BUILD_DIR = File.join(File.dirname(__FILE__), 'build')

task :deps do
  pkg = ENV['pkg']
  file = ['-beta', '-experimental', ''].
         map { |s| [pkg + s + '-min', pkg + s] }.
         flatten.
         map { |f| File.join(BUILD_DIR, pkg, f + '.js') }.
         find(&File.method(:file?))
  
  File.read(file).
  scan(/\b(?:YAHOO|Y)(?:\.[A-Za-z0-9\_\$]+)+(?:\s*=)?/).
  flatten.uniq.sort.
  each(&method(:puts))
end

