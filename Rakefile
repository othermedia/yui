BUILD_DIR = File.join(File.dirname(__FILE__), 'build')

task :deps do
  pkg = ENV['pkg']
  file = [pkg + '-beta', pkg + '-experimental', pkg].
         map { |f| File.join(BUILD_DIR, pkg, f + '.js') }.
         find(&File.method(:file?))
  
  File.read(file).
  scan(/\b(?:YAHOO|Y|lang|util|widget|tool)(?:\.[A-Za-z0-9\_\$]+)+(?:\s*=)?/).
  flatten.
  map { |s| s.gsub(/^YAHOO\./, '') }.
  uniq.sort.
  each(&method(:puts))
end

