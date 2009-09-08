BUILD_DIR = File.join(File.dirname(__FILE__), 'build')

task :deps do
  pkg = ENV['pkg']
  file = [pkg, pkg +'-beta', pkg + '-experimental'].
         map { |f| File.join(BUILD_DIR, pkg, f + '.js') }.
         find(&File.method(:file?))
  
  File.read(file).
  scan(/\b(?:YAHOO|Y)(?:\.[A-Za-z0-9\_\$]+)+/).
  flatten.uniq.sort.
  each(&method(:puts))
end

