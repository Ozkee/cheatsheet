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

