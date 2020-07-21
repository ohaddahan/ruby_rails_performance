# ruby_rails_performance

Ruby pitfalls

[Fast-Ruby](https://github.com/JuanitoFatas/fast-ruby)

[Fast-Ruby#String](https://github.com/JuanitoFatas/fast-ruby/blob/master/code/string/concatenation.rb)
<table border="1">
  <tr>
    <td>

```ruby
require 'benchmark/ips'

# 2 + 1 = 3 object
def slow_plus
  'foo' + 'bar'
end

# 2 + 1 = 3 object
def slow_concat
  'foo'.concat 'bar'
end

# 2 + 1 = 3 object
def slow_append
  'foo' << 'bar'
end

# 1 object
def fast
  'foo' 'bar'
end

def fast_interpolation
  "#{'foo'}#{'bar'}"
end
```
    </td>
<td>


```ruby
require 'benchmark/ips'
Benchmark.ips do |x|
  x.report('String#+')                 { slow_plus }
  x.report('String#concat')            { slow_concat }
  x.report('String#append')            { slow_append }
  x.report('"foo" "bar"')              { fast }
  x.report('"#{\'foo\'}#{\'bar\'}"')   { fast_interpolation }
  x.compare!
end
```
</td>

</tr>

</table>





**Native JSON generation from PostgreSQL:** https://gitlab.com/nativeson/nativeson

**Native pluck:** https://gitlab.com/nativepluck/nativepluck

**Fasterer Ruby:** https://github.com/DamirSvrtan/fasterer

**Rubucop Perf:** 
https://rubocop.readthedocs.io/en/latest/cops_performance/
https://github.com/rubocop-hq/rubocop-performance
https://github.com/airbnb/ruby/blob/master/rubocop-airbnb/config/rubocop-performance.yml


**Prevent DB calls from views :**	https://www.driftingruby.com/episodes/improving-partial-loading-performance

**Recommended Ruby/Rails APM :** https://github.com/scoutapp/scout_apm_ruby

**Recommended Ruby XML parser :** https://github.com/ohler55/ox

**Recommended JSON parsers :** https://github.com/ohler55/oj

**Recommended malloc :** https://github.com/mojodna/heroku-buildpack-jemalloc

**Bulk ActiveRecord operations :** https://github.com/zdennis/activerecord-import

**PostgreSQL DB performance dashboard :** https://github.com/ankane/pghero

**Memory profiler :** https://github.com/SamSaffron/memory_profiler

**N+1 detection :** https://github.com/flyerhzm/bullet

**Iteration Per Second benchmarks :** https://github.com/evanphx/benchmark-ips

**Proper Thread Pool :** https://github.com/meh/ruby-thread

**Free error tracking :** https://github.com/errbit/errbit

**Fastest Ruby HTTP client (multi thread) :** https://github.com/typhoeus/typhoeus

**DB profiling :** https://github.com/MiniProfiler/rack-mini-profiler

**Super efficient JSON using PostgreqSQL :** https://dockyard.com/blog/2014/05/27/avoid-rails-when-generating-json-responses-with-postgresql

