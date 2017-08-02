# Ruby

### Difference between ``` and ``` and ``` && ``` in Ruby?

``` and ``` is the same as ``` && ``` but with [lower precedence](http://phrogz.net/ProgrammingRuby/language.html#table_18.4). They both use [short-circuit evaluation](https://en.wikipedia.org/wiki/Short-circuit_evaluation).

WARNING: ``` and ``` even has lower precedence than ``` = ``` so you'll want to avoid and always


```
foo = :foo
bar = nil

a = foo and bar
# => nil
a
# => :foo

a = foo && bar
# => nil
a
# => nil

a = (foo and bar)
# => nil
a
# => nil

(a = foo) && bar
# => nil
a
# => :foo
```

The same thing works for ``` || ``` and ``` or ```.

### Difference between ``` public ```, ``` protected ```  and ``` private ``` in Ruby/Rails?
```
class Sibling
  def ask(sib)
    sib.tell
  end
  
  def spy_on(sib)
    sib.secret # will always complain
  end

  protected

  def tell
    secret
  end
  
  private
  
  def secret
    "Charlie tooted"
  end
end

rose  = Sibling.new
ricky = Sibling.new

begin
  puts ricky.tell
rescue
  puts "Ricky will only tell another sibling"
end

begin
  puts rose.spy_on(ricky)
rescue
  puts "Ricky complains when Rose tries to find the secret"
end

puts rose.ask(ricky) # Ricky will tell if Rose asks nicely
```
---

# Integration Tests

``` ruby -I test test/unit/.. ```

---

# Rspec

``` rake db:test:prepare ```

``` rspec spec/ ```

---

# Git

``` git log origin/master..HEAD ```

``` git reset --hard origin/master ```

``` git rebase -i origin/master ```

---

# ElasticSearch

``` Model.__elasticsearch__.create_index! force: true ```

``` Model.import ```

---

# Set Custom Domain to localhost

In /etc/hosts ``` sudo vim /etc/hosts ``` add for example:

``` 127.0.0.1   www.example.com ```

To clear the cached entry, run this on the command line:

``` dscacheutil -flushcache ```

[Stackoverflow](https://stackoverflow.com/questions/7576217/assigning-a-domain-name-to-localhost-for-development-environment-on-mac-os-x-wit)

[lvh.me](https://www.quora.com/What-is-lvh-me)
