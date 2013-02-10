require 'listen'

desc "Reload"
task :reload do
  Listen.to("./", :ignore => %r{^_site/}) do |modified, added, removed|
    if modified.grep(/\.scss$/).any?
      puts "Sassy"
      `sass assets/stylesheets/app.scss assets/stylesheets/app.css`
    else
      puts "Jekylling"
      `jekyll`
    end
  end
end

desc "Deploy"
task :deploy do
  puts `ls -l _deploy/ | grep -v '.git' | xargs rm -rf`
end
