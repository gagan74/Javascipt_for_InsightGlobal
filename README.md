#Javascipt_for_InsightGlobal

Below are the questions and answers asked for the questions:

JavaScript Coding: Write a multiplication function in javascript to use like this.

function mul(...rest) {
	var product = 1;
	function mul(...rest) {
		product *= rest.reduce((acc,item)=>acc*item,1);
		return mul;
	}
	mul.valueOf = function valueOf(){
		return product;
	};
	return mul(...rest);
}

console.log(mul(2)(4)(5));
//------------------------------------------------------------------------------------------------------------------------------
React Coding: Write a countdown clock react component that has a function prop that will format the time it displays.

class Example extends React.Component {
  constructor(props) {
    super(props);
    this.state = { time: {}, seconds: props.seconds };
    this.intervalValue = 0;
    this.startTimer = this.startTimer.bind(this);
    this.countDown = this.countDown.bind(this);
  }

  startTimer() {
    if (this.intervalValue == 0) {
      this.intervalValue = setInterval(this.countDown, 1000);
    }
  }

  countDown() {
    let seconds = this.state.seconds - 1;
    this.setState({
      seconds: seconds,
    });
    
    // Check if we're at zero.
    if (seconds == 0) { 
      clearInterval(this.timer);
    }
  }

  render() {
    return(
      <ShowTime seconds={this.state.seconds} startTimer={this.startTimer}  />
    );
  }
}

function formatTime(seconds){
    let hours = Math.floor(seconds / (60 * 60));
    let inMinutes = seconds % (60 * 60);
    let minutes = Math.floor(inMinutes / 60);
    let inSeconds = inMinutes % 60;
    let sec = Math.ceil(inSeconds);

    let obj = {
      "hours": hours,
      "minutes": minutes,
      "seconds": sec
    };
    return obj;
}

function ShowTime({seconds, startTimer}){
	let time = formatTime(seconds);
  return <div>
        <button onClick={startTimer}>Start</button>
        h: {time.hours} m: {time.minutes} s: {time.seconds}, In seconds: {seconds}
      </div>

}

// How to use this component as an example

ReactDOM.render(
  <Example seconds={500}/>,
  document.getElementById('container')
);

 

Which of the following code snippet append an element value at the end of the array, arr?

a) arr[arr.length+1] = value; // it increases value length by 1 and adds value at end

b) arr[arr.length] = value                               

c) arr[arr.length - 1] = value

d) arr = arr + value

Expected by me  ANSWER= (a) 

//--------------------------------------------------------------------------------------------------------------------------------------//
JavaScript: what is the correct way to create a JavaScript array?

a) var items = ["Orange", "Apple"]; // correct syntax

b) var items = {"Orange", "Apple"}; // not correct

c) var items = new array("Orange", "Apple"); // new Array // lower case 'a' is not correct               

d) var items[] = {"Orange", "Apple"}; // same as b 

 
Expected by me  ANSWER= (a) 
//-------------------------------------------------------------------------------------------------------------------------------//
JavaScript: What is the output of the following code

foo = 1;

(function() {

   foo = 2; // global variable is being set to 2. The value is not being modified

})();

var x = function () {

  foo = 3;                                           

};

(function() {

   var foo = 4;

})();

console.log(foo);

Expected by me ANSWER= 2 
 
