# Capistrano Colorized Stream

testing ruby: 1.9.3; Capistrano: > 2.0

## About capistrano-colorized-stream 

capistrano-colorized-stream adds a feature to append colorized hostnames at the head of each line for the [capistrano](https://github.com/capistrano/capistrano)'s `stream` method. 

With this gem, it enables you to watch logs on multiple deploying hosts concurrently with colored hostnames like [foreman](https://github.com/ddollar/foreman), for example.

## USAGE

For example, to stream /var/log/syslog files located on multiple hosts, use the extended `stream` method at config/deploy.rb as:

```ruby
require 'capistrano/colorized_stream'

server host1, :web
server host2, :web

task :syslog, :roles => :web do
  stream "tail -f /var/log/syslog"
end
```

Then, execute the defined capistrano task

    $ bundle exec cap syslog

Below is an example of results.

![capistrano-colorized-stream.png](https://f.cloud.github.com/assets/2290461/68476/308c50de-5f35-11e2-8f5d-61b1dd62626a.png)


## License

MIT License

## Acknowledgement

Special thanks to [@niku4i](http://orihubon.com/blog/2012/02/09/streaming-log-with-capistrano/).
