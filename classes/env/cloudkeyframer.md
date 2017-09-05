---
title: The Cloud Keyframer
layout: reference
weight: 0
---
The Cloud Keyframer<br>========<br>Previous: <sky\_keyframer>

Updating
--------
Two instances of CloudKeyframer are stored in simul::clouds::Environment - one for 3D volumetric clouds and one for 2D high-altitude clouds.
As a keyframer, this class stores a list of keyframes; this list can be modified at runtime, or loaded from a sequence (see <man\_6\_sequencer>).

The keyframes each have a **time** value, and the keyframer tracks a current time through these frames, interpolating properties as it does so, into a special keyframe.
You can be obtain a reference to this using ::clouds::CloudKeyframer::GetInterpolatedKeyframe() GetInterpolatedKeyframe()\endlink.

The cloud keyframer is updated from ::clouds::Environment Environment\endlink.

Some ::clouds::CloudKeyframe cloud keyframe are used as per-keyframe values to generated the 3D or 2D cloud textures.
These textures are then interpolated for rendering:

- cloudiness
- distribution_base_layer
- distribution_transition
- upper_density
- cloud_height_km
- octaves
- persistence
- extinction
- diffusivity
- masks

Some are used as interpolated values per-frame when rendering, either to determine the geometry of the clouds:
- wind_speed
- wind_direction
- cloud_base_km
- cloud_height_km
- cloud_width_km
- offsetx
- offsety

or the visual cloud properties:

- direct_light
- indirect_light
- ambient_light
- light_asymmetry
- fractal_amplitude
- fractal_wavelength
- edge_sharpness
- churn
- base_noise_factor

While others are used to inform different parts of the rendering system:
- precipitation
- rain_to_snow
- lightning
- godray_strength

Cloud Volume Size
------------
By default, the cloud volume repeats at the edges, and the volume width is controlled by the keyframe cloud_width_km value.
You can change the size of this volume freely, but to increase the size while retaining the same level of detail, you will also need to modify the size of the volumetric grid.

For example, to double the size of the volume, select all the 3D cloud keyframes, and double the size of cloud_width_km. Select the cloud layer, and increase both the Cloud Grid Width, and the Generation Noise Resolution, by a factor of two.

Fine Control
------------
The cloud shape can be controlled using the keyframe properties ::clouds::CloudKeyframe::distribution_base_layer distribution_base_layer\endlink,
::clouds::CloudKeyframe::distribution_transition distribution_transition
::clouds::CloudKeyframe::upper_density upper_density\endlink.

Local Cloud Cells
------------
**Clouds** can be positioned precisely using the masking feature of cloud keyframes.

To position clouds, disable horizontal wrapping and enable explicit offsets, so that the cloud volume can be positioned
per-keyframe:

        environment->cloudKeyframer->SetExplicitOffsets(true);
        environment->cloudKeyframer->GetCloudInterface()->SetWrap(false);

e.g. to position the fourth keyframe of the cloudKeyframer:

        simul::clouds::CloudKeyframe *K=environment->cloudKeyframer->GetKeyframe(3);
        K->offsetx=10000.f;
        K->offsety=10000.f;

Within the cloud volume, the **masks** determine where clouds are present at any horizontal position. 
Each keyframe has an optional list of masks, and each mask has an xy position, and a radius, in units where 1.0 is
the width of the volume. Each mask has a thickness, from 0 to 1.0, which acts as a multiplier to the local humidity (i.e. cloudiness).

The mask list is a **map**, with an integer key. For example, to modify keyframe K, we can create or change the mask with id 7:

        simul::clouds::Mask &M=K->masks[7];
        M.x=0.5f;
        M.y=0.6f;
        M.radius=0.3f;
        M.thickness=1.0f;

To remove a mask from a keyframe:

        K->masks.erase(7);

<hr>
Next: <a href="../shaders">Shaders</a>
