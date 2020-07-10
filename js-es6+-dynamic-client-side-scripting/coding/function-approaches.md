# Function Approaches

## Write a sample of callback function

```javascript
function writeBlog(topic, callback) {
    console.log(`Starting my ${topic} blog.`);
    // then execute the callback function that was passed
    callback();
}

writeBlog('JS', function() {
    console.log('Finished my blog!');
});
```

