# FullCalendarWithGoogleCalendarEventsAtGatsby
<!-- AUTO-GENERATED-CONTENT:START (STARTER) -->
<h1 align="center">
  Implementation of FullCalendar to GatsbyJS, with the usage of GoogleCalendarAPI
</h1>

## 🚀 Quick start

1.  **Create a Gatsby site.**

    Use the Gatsby CLI to create a new site, specifying the default starter.

    ```shell
    # create a new Gatsby site using the default starter
    gatsby new my-default-starter https://github.com/gatsbyjs/gatsby-starter-default
    ```
    
1.  **Open the source code and start editing!**

    Your site is now running at `http://localhost:8000`!

    _Note: You'll also see a second link: _`http://localhost:8000/___graphql`_. This is a tool you can use to experiment with querying your data. Learn more about using this tool in the [Gatsby tutorial](https://www.gatsbyjs.org/tutorial/part-five/#introducing-graphiql)._

    Open the `my-default-starter` directory in your code editor of choice and edit `src/pages/index.js`. Save your changes and the browser will update in real time!

## THE CODE TRY SOME 

```
import React, {useState} from "react"
import { GlobalStyle } from "../components/styles/GlobalStyles";
import HomeBar from "../components/HomeBar";
import Footer from "../components/Footer";
import styled from "styled-components";

import FullCalendar from "@fullcalendar/react";
import dayGridPlugin from "@fullcalendar/daygrid";
import timeGridPlugin from "@fullcalendar/timegrid";
import interactionPlugin from "@fullcalendar/interaction";
import googleCalendarPlugin from '@fullcalendar/google-calendar';

// trzeba importować css do kazdego plugina manualnie
import "@fullcalendar/daygrid/main.css";
import "@fullcalendar/timegrid/main.css";

// import 'bootstrap/dist/css/bootstrap.min.css';
// import Button from 'react-bootstrap/Button';
// import Modal from'react-bootstrap/Modal'

const BookingCalendar = () => {

    // const [displayModal, setDisplayModal] = useState(false);
    // const [eventModal, setEventModal] = useState([]);
    // const hideModal = () => setDisplayModal(false);
  

  return ( 
    <>
    <GlobalStyle></GlobalStyle>
    <HomeBar></HomeBar>
  
       {/* {
         eventModal.map( (event, id) =>(
          <Modal show={displayModal} onHide={hideModal} key={id}>
          <Modal.Header closeButton>
            <Modal.Title>Trening</Modal.Title>
          </Modal.Header>
          <Modal.Body>
            <h4>{event.title}</h4>
            <h4>{event.website}</h4>
            <p>{event.start.toString()}</p>
            <p>{event.allDay.toString()}</p>
            </Modal.Body>
          <Modal.Footer>
            <Button variant="secondary" onClick={hideModal}>
              Close
            </Button>
            <Button variant="primary" onClick={hideModal}>
              Save Changes
            </Button>
          </Modal.Footer>
           </Modal>
         ))
         
       }  */}
         <CalendarContainer lightBg="true">
        <CalendarWrapper>
          <FullCalendar
              defaultView="dayGridMonth"
              header={{
                left: "today, prev,next",
                center: "title",
                right: "dayGridMonth,timeGridWeek,timeGridDay,listWeek"
              }}
              plugins={[dayGridPlugin, timeGridPlugin, interactionPlugin, googleCalendarPlugin]}
              googleCalendarApiKey=' '
              eventSources={[
                {
                        googleCalendarId:" "
                      },
                ]}
              // eventClick={(e)=>{
              //   if(e){
              //     setDisplayModal(true)
              //     setEventModal([e.event])
              //     console.log(e.event)
              //   }
              // }}
            />
          </CalendarWrapper>
      </CalendarContainer>
  
  
  
  <Footer />
  </>
  )
};

const CalendarContainer = styled.div`
  color: #fff;
  background: ${({ lightBg }) => (lightBg ? "#0c0c0c" : "#010606")};

  @media screen and (max-width: 768px) {
    padding: 100px 0;
  }
`;

const CalendarWrapper = styled.div`
  display: grid;
  z-index: 1;
  height: 860px;
  width: 100%;
  max-width: 1100px;
  margin-right: auto;
  margin-left: auto;
  padding: 0 24px;
  justify-content: flex;
`;

export default BookingCalendar;

```

## 🎓 Learning Gatsby

Looking for more guidance? Full documentation for Gatsby lives [on the website](https://www.gatsbyjs.org/). Here are some places to start:

- **For most developers, we recommend starting with our [in-depth tutorial for creating a site with Gatsby](https://www.gatsbyjs.org/tutorial/).** It starts with zero assumptions about your level of ability and walks through every step of the process.

- **To dive straight into code samples, head [to our documentation](https://www.gatsbyjs.org/docs/).** In particular, check out the _Guides_, _API Reference_, and _Advanced Tutorials_ sections in the sidebar.

## 💫 Deploy

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/gatsbyjs/gatsby-starter-default)

<!-- AUTO-GENERATED-CONTENT:END -->
