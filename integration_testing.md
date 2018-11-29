## Integration Testing 

### Cucumber 
Keyword | What it do 
------- | ---
`given` | precondition 
`and`   | 
`when`  | action 
`and`   |
`then`  | results 

- Example tables (loop), step tables (all at once)
- Scenario outline 
- Background - executes first 
- Step definition - machine params to code, simulating click/interaction. Can only match one thing. 
- "be matchers" 

### rspec 

```Ruby 
describe 
    context ______ do 
        it ______ do 
            expect (______).to ...
        end
    end
end
```

### Capybara 

```Ruby 
Feature 
    Scenario 
        Given 
        Then 
    Scenario 
        Given 
        Then 
```