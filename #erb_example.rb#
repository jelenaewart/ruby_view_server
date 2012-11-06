require 'erb'

x = 42
template = ERB.new "The value of x is: <%= x %>"
puts template.result(binding)

temp2 =  %q{
  % animals.each do |pet|
    <%= "#{pet} are great"  %>
  % end
}.gsub(/^  /, '')

animals = ["cats", "dogs"]
sharkplate = ERB.new(temp2, 0, "%<>")

puts sharkplate.result(binding)

# Create template.
template = %q{
  From:  James Edward Gray II <james@grayproductions.net>
  To:  <%= to %>
  Subject:  Addressing Needs

  <%= to[/\w+/] %>:

  Just wanted to send a quick note assuring that your needs are being
  addressed.

  I want you to know that my team will keep working on the issues,
  especially:

  <%# ignore numerous minor requests -- focus on priorities %>
  % priorities.each do |priority|
    * <%= "#{priority}"  %>
  % end

  Thanks for your patience.

  James Edward Gray II
}.gsub(/^  /, '')

message = ERB.new(template, 0, "%<>")

# Set up template data.
priorities = [ "Run Ruby Quiz",
               "Document Modules",
               "Answer Questions on Ruby Talk" ]
to = "Community Spokesman <spokesman@ruby_community.org>"

# Produce result.
email = message.result
puts email
