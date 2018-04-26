We can update the UI with states and its the example while clicking on button its 'change the content' and while updating the input shows the two way data binding.

We're importing only useful files here...

index.js:: update the file

import React from 'react';
import {render} from 'react-dom';
import {Header} from './header';
import {Footer} from './footer';
import './index.css';

class App extends React.Component{

	constructor(){
		super();
		this.state = {
			name:'DefaultName'
		}
	}


	showName(passName){
		this.setState({
			name:passName
		})
	}

	changeName(e){
		this.setState({
			name:e.target.value
		})
	}


	render(){
		return(
<div className="container">
	<div className="row">
		<div className="col-xs-12">

		<p>{this.state.name}</p>
	event change to click on button and its happening in same component:: <button onClick={this.showName.bind(this,'hello')} className="btn btn-primary">Click Me</button>
			<hr/><hr/>
			<Header/>

			<hr/><hr/>

Two way data binding:: <input type="text" value={this.state.name} onChange={this.changeName.bind(this)}/>

		</div>
	</div>
	<div className="row">
		<div className="col-xs-12">
			<h1>This is the first component along with multiple component</h1>
		</div>
	</div>
    <div className="row">
	  <div className="col-xs-12">
		<Footer/>
	 </div>	
	</div>
</div>
		)
	}
}

render(<App />, document.getElementById('root'));

