#Code signing fails for Enterprise distribution #90

Thank you so much for your very detailed report. Could you try updating to the latest gym and use the new option:

sigh --export_method enterprise
or in your Fastfile

sigh(export_method: 'enterprise')



I'm still building with Fastlane, therefore the revalant part of my Fastfile now looks like this:

  sigh({
    app_identifier: ENV["BUNDLE_IDENTIFIER"],
    username: ENV["APPLE_ID"],
    team_id: ENV["APPLE_TEAM_ID"],
    output_path: ENV["BUILD_PATH"]
  })

  ENV["PROFILE_UDID"] = lane_context[SharedValues::SIGH_UDID]

  gym(
    clean: true,
    export_method: 'enterprise',
    output_directory: ENV["BUILD_PATH"],
    output_name: "Welkio-#{lane_context[SharedValues::BUILD_NUMBER]}",
    scheme: "Welkio"
  )
  
  
  
  
  
  
##Here is my gym setup:

    gym(
      scheme: "Scrubbed",
      codesigning_identity: "Scrubbed",
      provisioning_profile_path: provisioning_profile_path,
      include_bitcode: false,
      export_method: "enterprise",
      clean: false
    )
    
    
    
    ##Export Failed with Xcode 7 - `No applicable devices found` #104

    
    gym(scheme: "MyProj AdHoc", sdk: "iphoneos9.0", use_legacy_build_api: true)
    
    
    
    
    
##configuration:
    
      sigh({
    app_identifier: ENV["BUNDLE_IDENTIFIER"],
    username: ENV["APPLE_ID"],
    team_id: ENV["APPLE_TEAM_ID"],
    output_path: ENV["BUILD_PATH"]
	  })
	
	  ENV["PROFILE_UDID"] = lane_context[SharedValues::SIGH_UDID]
	
	  gym(
	    clean: true,
	    export_method: 'enterprise',
	    output_directory: ENV["BUILD_PATH"],
	    output_name: "Welkio-#{lane_context[SharedValues::BUILD_NUMBER]}",
	    scheme: "Welkio"
	  )