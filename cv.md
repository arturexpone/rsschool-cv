1.  #### Artur Matveev
2.  #### Contact Info
    * Mobile phone - **+375 (29) 835 61 42**
    * Linkedin - [click](https://www.linkedin.com/in/artur-matveev-23b4811a6)
    * Telegram - [click](https://t.me/TrueStory1337)
    * Viber - [click](viber://chat?number=%2B375298356142)
3.  #### Summary
    I am 24 years old. I live in Minsk. 
    I have a technical secondary special education, currently I am a 5th-year student of the University. 
    I study in absentia at the faculty of international law and legal psychology.
    A result-oriented, meticulous novice web developer with non-commercial experience in creating various web 
    applications using **HTML, CSS, JavaScript, React, Redux**, and other technologies.
    I have been studying the above-mentioned technology stack since mid-2019. 
    I first got into web development when trying to connect third-party services for the client (CRM). 
    Since that time, I have been regularly engaged in self-education in the field. 
    I am not afraid of complex tasks, and the more I learn about how web applications work, 
    the more interest they arouse in me :) At the time of writing this portfolio, 
    I can independently create fullstack applications with a level of complexity - up to average, 
    using popular libraries that are often used in production.
    I know English at a low level and I'm already in the process of *fixing this bug* :)
4. #### Skills
    * HTML
    * CSS
    * JavaScript
    * React
    * Node JS
    * WebPack (low-level)
    --- ---
    Packages/libraries that I worked with, but I have a superficial knowledge of:
    * Mongoose
    * Axios
    * Socket.io
    * Fuzzy-search
    * Redux
    * Express
    * Material-UI
    * Firebase
    * cuid
    * semantic-ui-react
5. #### Code examples
      JavaScript (React) code:
    
    ```javascript
    
    import React, {useEffect, useState} from 'react';
    import {NavLink} from 'react-router-dom';
    import {compose} from 'redux';
    import {firestoreConnect} from 'react-redux-firebase';
    import {connect} from 'react-redux';
    
    import {Loader} from '../layout/Loader';
    import {createInput} from '../utils';
    
    
    const EditClient = (props) => {
    
      const { client, history, firestore, settings } = props;
    
      let initialState = {
        firstName: '',
        lastName: '',
        email: '',
        phone: '',
        balance: '',
      };
    
      const [state, setState] = useState(initialState);
    
      useEffect(() => {
        if (localStorage.getItem('uid') === '') {
          history.push('/login');
        }
      });
    
      if(!client) {
        return <Loader />
      }
    
      if (client.firstName && state.firstName === '') {
        setState(client);
      }
    
      let readyMountInput = [];
    
      if (client) {
        readyMountInput = createInput([
          ['First Name','text', 'firstName'],
          ['Last Name','text', 'lastName'],
          ['Email', 'email', 'email'],
          ['Phone', 'text', 'phone'],
          ['Balance','text', 'balance', settings.disableBalanceOnEdit],
        ], state, setState);
      }
    
      const onSubmit = (e) => {
        e.preventDefault();
        firestore.update({collection: 'clients', doc: client.id}, state)
          .then(res => history.push('/'));
      }
    
      return (
        <div>
          <div className='row'>
            <div className='col-md-6'>
              <NavLink to='/' className='btn btn-link'>
                <i className='fas fa-arrow-circle-left'> </i> Back to dashboard
              </NavLink>
            </div>
          </div>
    
          <div className='card-header'>Edit client</div>
          <div className='card-body'>
            <form onSubmit={onSubmit}>
              {readyMountInput}
    
              <input type='submit' value='Submit' className='btn btn-primary btn-block'/>
            </form>
          </div>
        </div>
      )
    }
    
    export default compose(firestoreConnect((props) => [{
        collection: 'clients',
        storeAs: 'client',
        doc: props.match.params.id
      }]),
      connect(({ firestore: { ordered }, settings, notify, firebase }, props) => ({
        client: ordered.client && ordered.client[0],
        settings,
        auth: firebase.auth
      })))(EditClient);
    
    ```
    ##### More examples of my work can be found here: [click](https://arturexpone.netlify.app/projects)
6. #### Experience
    I have some non-commercial experience.
    * Create a simple SPA.
    * Creating simple servers on Node JS (CRUD).
    * Implementation of server data exchange between two services (CRM [oauth 2.0 authorization is used] and courier delivery service).
    * Development of simple applications within the Bitrix 24 CRM ecosystem, using the REST API.
    * Build online stores on CMS 1c-Bitrix and Wordpress, connect payment systems to them, deploy on hosting,
     install SLL certificates, etc
     ---
    Source code for some projects:
     1. [Client-panel (React & Redux & Firebase)](https://github.com/arturexpone/client-panel)
     2. [Messenger (React & Redux & Socket.io & Mongo)](https://github.com/arturexpone/messenger)
     3. [Excel (Native JS)](https://github.com/arturexpone/excel)
     4. [Contact manager (React & Redux & Thunk & Bootstrap)](https://github.com/arturexpone/contact-manager)
     5. [Game [rock-paper-scissors] (Native JS)](https://github.com/arturexpone/rock-paper-scissors)
     6. [Sorting data of random users (Native JS)](https://github.com/arturexpone/sorting-data-of-random-users)
     7. [Seat reservation (Native JS)](https://github.com/arturexpone/seat-reservation)
     8. [Drag-drop list (Native JS)](https://github.com/arturexpone/drag-drop-list)
7. #### Education 
    Secondary special technical education, graduated in 2014.
    At the moment, I am receiving higher education (in absentia, 5th year).
    Completed the following courses:
    1. HTML Academy (paid and free, html & css & js).
    2. React, path of the samurai 1.0.
    3. FreeCodeCamp (partially).
    4. 6 kata on codewars.
    5. Some courses on udemy.
8. #### English
    There was no practice in English, I studied German at school.
    I am engaged in independent study, at the moment level A2.