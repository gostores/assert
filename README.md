# Golang assert library

## How to use
```
  package yours

  import (
    "testing"
    "github.com/govenue/assert"
  )

  func TestSomething(t *testing.T) {

    // assert equality
    assert.Equal(t, 123, 123, "they should be equal")

    // assert inequality
    assert.NotEqual(t, 123, 456, "they should not be equal")

    // assert for nil (good for errors)
    assert.Nil(t, object)

    // assert for not nil (good when you expect something)
    if assert.NotNil(t, object) {

      // now we know that object isn't nil, we are safe to make
      // further assertions without causing any errors
      assert.Equal(t, "Something", object.Value)

    }

  }
```

if you assert many times, use the below:

```
  package yours

  import (
    "testing"
    "github.com/govenue/assert"
  )

  func TestSomething(t *testing.T) {
    assert := assert.New(t)

    // assert equality
    assert.Equal(123, 123, "they should be equal")

    // assert inequality
    assert.NotEqual(123, 456, "they should not be equal")

    // assert for nil (good for errors)
    assert.Nil(object)

    // assert for not nil (good when you expect something)
    if assert.NotNil(object) {

      // now we know that object isn't nil, we are safe to make
      // further assertions without causing any errors
      assert.Equal("Something", object.Value)
    }
  }
```

## License
Base on [testify/assert](https://github.com/stretchr/testify/assert), Thanks stretchr.
