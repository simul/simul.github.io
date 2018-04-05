---
title: The Plugin Rendering Interface
layout: reference
weight: 40
---
The Plugin Rendering Interface
===

=========================<br>=========================

Previous: <a href="rendering">Rendering the Environment</a>
<hr size="1">

One way to connect trueSKY to a game or simulation engine is using the Plugin Rendering Interface.
A dynamic link library or dll called PluginRenderInterface.dll (or similar) is loaded, dynamically, from within the game engine.
The exported functions are used to perform sky rendering per-frame for each view.

	int  StaticInitInterface();
	void StaticSetMemoryInterface(MemoryInterface *);
	int  StaticShutDownInterface(  );
	void StaticSetDebugOutputCallback(FLogCallback);
	void StaticSetGraphicsDevice(void* device, GraphicsDeviceType deviceType,GraphicsEventType eventType);
	int  StaticPushPath(const char*,const char*);
	void StaticSetFileLoader(simul::base::FileLoader *);
	int  StaticGetOrAddView( void *);
	int  StaticGetLightningBolts(LightningBolt *,int maxb);
	int  StaticSpawnLightning(const float startpos[3],const float endpos[3],float magnitude,const float colour[3]);
	int  StaticRenderFrame(void* device,void* deviceContext,int view_id
		,float* viewMatrix4x4
		,float* projMatrix4x4
		,void* depthTexture
		,void* depthResource
		,int4 depthViewport
		,const Viewport *v
		,PluginStyle s
		,float exposure
		,float gamma
		,int framenumber
		,const float *nvMultiResConstants);
	int StaticCopySkylight(void *pContext
												,int cube_id
												,float* shValues
												,int shOrder
												,void *targetTex
												,const float *engineToSimulMatrix4x4);
	int StaticRenderOverlays(void* device,void* deviceContext,void* depthTexture,const float* viewMatrix4x4,const float* projMatrix4x4,int view_id);
	int StaticTick( float deltaTime );
	int StaticOnDeviceChanged( void * device );
	void* StaticGetEnvironment();
	int StaticSetSequence( std::string sequenceInputText );
	class UE4PluginRenderInterface* StaticGetRenderInterfaceInstance();
	void StaticSetPointLight(int id,const float pos[3],float radius,float maxradius,const float radiant_flux[3]);
	void StaticCloudPointQuery(int id,const float *pos, VolumeQueryResult *res);
	void StaticCloudLineQuery(int id,const float *startpos,const float *endpos, LineQueryResult *res);
	
	voidStaticSetRenderTexture(const char *name, void* texturePtr);
	voidStaticSetMatrix4x4(const char *name, const float []);
	
	void StaticSetRender( const char *name,int num_params,const Variant32 *params);
	void StaticSetRenderBool( const char *name,bool value );
	bool StaticGetRenderBool( const char *name );
	void StaticSetRenderFloat( const char *name,float value );
	float StaticGetRenderFloat( const char *name );
	
	void StaticSetRenderInt( const char *name,int value );
	int StaticGetRenderInt( const char *name,int num_params,const Variant32 *params);

	void StaticSetRenderString( const char *name,const FString &value );
	void StaticGetRenderString( const char *name ,char* value,int len);
	bool StaticTriggerAction( const char *name );
	
	
	void StaticExportCloudLayerToGeometry(const char *filenameUtf8,int index);

	void StaticSetKeyframeFloat(unsigned,const char *name, float value);
	float StaticGetKeyframeFloat(unsigned,const char *name);
	void StaticSetKeyframeInt(unsigned,const char *name, int value);
	int StaticGetKeyframeInt(unsigned,const char *name);

	float StaticGetRenderFloatAtPosition(const char* name,const float *pos);

	bool StaticFillColourTable(unsigned uid,int x,int y,int z,float *target);

<hr>
Next: <a href="classes">The trueSKY Classes</a>
