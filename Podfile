platform :ios, '9.0'
use_frameworks!

target 'CentralManager' do
  pod 'BlueCapKit', '~> 0.5.2'
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    puts "TARGET: #{target.name}"
    target.build_configurations.each do |config|
      puts "SETTING CONFIG: #{config.name}"
      config.build_settings['SWIFT_VERSION'] = '3.0'
      if config.name == 'Debug'
        config.build_settings['OTHER_SWIFT_FLAGS'] ||= ['$(inherited)', '-D DEBUG']
      end
    end
  end
end
