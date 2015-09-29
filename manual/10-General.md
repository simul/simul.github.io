Licensing {#licensing}
===========
Set your licence key with:
		
    simul::base::SetLicence("XXXXXXXXX");

- best done before creating your Environment object.
There are some useful functions for licence testing, they are in Simul/Base/EnvironmentVariables.h:

You can retrieve the set licence with:

        const char *licence=simul::base::GetLicence();

You can check licence validity with

        const char *result=simul::base::GetLicenceValidityText(licence);

You can get an enum result with

    simul::base::FeatureLevel f=simul::base::GetFeatureLevel();
	
Or retrieve information on the specified licence key:

	simul::base::LicenceInfo licenceInfo=simul::base::GetLicenceInfo( *lic);