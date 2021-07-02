platform :ios, '9.0'
use_frameworks!
inhibit_all_warnings!
target 'Dubbing' do
  pod 'MJExtension'
  
  pod 'MBProgressHUD'
  
  pod 'Masonry'
  
  pod 'YYCategories'
  pod 'YYCache'
  
  pod 'Google-Mobile-Ads-SDK'
  
  pod 'JCore', '2.1.4-noidfa'
  pod 'JPush', '3.2.4-noidfa'
  pod 'AFNetworking'
  
#  pod 'UMCommon'
#  pod 'UMCCommonLog'
#  pod 'UMDevice'
end

# 消除第三方库最低版本的警告，对第三方库进行了判断若DEPLOYMENT_TARGET<9.0就会切换成9.0
post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['OTHER_C_FLAGS'] = ['-Xclang', '-fcompatibility-qualified-id-block-type-checking']
      if config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'].to_f < 9.0
        config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = '9.0'
      end
    end
  end
end
