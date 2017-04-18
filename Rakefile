require "bundler/gem_tasks"
task :default => :spec

require "open-uri"
require "hive_thrift_cli/version"

TAG = "rel/release-#{HiveThriftCli::VERSION}"
SOURCE_URI = "https://raw.githubusercontent.com/apache/hive/#{TAG}/service-rpc/if/TCLIService.thrift"
THRIFT_FILE = "TCLIService.thrift"

namespace :thrift do
  task :download do
    open(SOURCE_URI) do |src|
      body = src.read.sub(/(?=^namespace.*\n)/m, "namespace rb #{HiveThriftCli}\n")
      File.write(THRIFT_FILE, body)
    end
  end
  
  task :compile => :download do
    system("thrift --gen rb:namespaced #{THRIFT_FILE}")
  end

  task :deploy => :compile do
    cp(Dir["gen-rb/hive_thrift_cli/*"], "lib/hive_thrift_cli", verbose: true)
  end
end

task :thrift => "thrift:deploy"
