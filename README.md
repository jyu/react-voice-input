Source: https://www.npmjs.com/package/react-voice-input

Continuing envato project for increase compatibility

# react-voice-input
Voice input component for React.JS

### Installation

```sh
$ npm install react-voice-input
```

### Usage

```js
import ReactVoiceInput from 'react-voice-input'
import React from 'react'

class MyApp extends React.Component {
  constructor (props) {
    super(props)
    this.state = {
      inputText: ''
    }

    this.onResult = this.onResult.bind(this)
    this.onInputChange = this.onInputChange.bind(this)
  }

  onInputChange (event) {
    this.setState({
      inputText: event.target.value
    })
  }

  onResult (result) {
    this.setState({
      inputText: result
    })
  }

  render () {
    const onEnd = () => {
      console.log('on end')
    }
    return (
      <main>
        <ReactVoiceInput
          onResult={this.onResult}
          onEnd={onEnd}
        >
          <input type='text' value={inputText} onChange={this.onInputChange} />
        </ReactVoiceInput>
      </main>
    )
  }
}
```

### API
* `onSpeechStart()` - optional callback function to detect speech start
* `onResult(value)` - callback function when get value from speech
* `onEnd()` - optional callback function when the speech end
* `onError(event)` - optional callback function when there's an error
* `containerClassName` - optional, the class name apply to the container, default to `rvi-contianer`
* `microphoneClassName` - optional, the class name apply to microphone, default to `rvi-microphone`
* `microphoneStyle` - optional inline style for the button

For how to use it, check the `example` folder.

### Run example

```sh
$ cd example
$ yarn
$ yarn run dev
```

Then go to http://localhost:3000/ in browser.

### License

MIT
