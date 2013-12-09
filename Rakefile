# Gem Requirements
require 'yaml'
require 'twilio-ruby'
load 'silly_titles.rb'

CREDENTIALS = YAML.load_file('credentials.yml')
TWILIO_SID = CREDENTIALS['twilio_sid']
TWILIO_AUTH = CREDENTIALS['twilio_auth']
PHONE_NUMBER = CREDENTIALS['twilio_number']
CLIENT = Twilio::REST::Client.new TWILIO_SID, TWILIO_AUTH

namespace 'twilio' do
  desc 'spit out credentials'
  task :creds do
    puts TWILIO_SID
    puts TWILIO_AUTH
    puts PHONE_NUMBER
  end
  desc 'text a fool'
  task :text_fool do
    CLIENT.account.messages.create({
      :to => '+18588292412',
      :from => PHONE_NUMBER,
      :body => new_title
    })
  end
end 
