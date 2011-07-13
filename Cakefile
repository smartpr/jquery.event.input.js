{print} = require 'sys'
{exec, spawn} = require 'child_process'

build = (watch) ->
	options = '--output lib/ --compile src/'.split ' '
	options.unshift '--watch' if watch
	lib = spawn 'coffee', options
	lib.stdout.on 'data', print
	lib.stderr.on 'data', print
	
	options = '--output test/lib/ --compile test/src/'.split ' '
	options.unshift '--watch' if watch
	test = spawn 'coffee', options
	test.stdout.on 'data', print
	test.stderr.on 'data', print

task 'build', 'Compile CoffeeScript source to JavaScript', ->
	build()

task 'dev', 'Compile continuously', ->
	build yes
