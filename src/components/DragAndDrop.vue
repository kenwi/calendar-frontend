<template>
<div id="wrap">
  <div id="external-events">
    <Container @drop="onDrop">
      <Draggable v-for="item in items" :key="item.id">
        <div class="draggable-item fc-event">{{ item.data }}</div>
      </Draggable>
    </Container>
  </div>
  <full-calendar :events="events" ref="calendar" />
</div>
</template>

<script>

import { Container, Draggable } from 'vue-smooth-dnd'

export default {

  name: 'DragAndDrop',
  components: { Container, Draggable },
  data () {
    return {
      header: 'Drag & Drop area',
      items: [
        {
          id: 0,
          data: 'Item 0'
        },
        {
          id: 1,
          data: 'Item 1'
        },
        {
          id: 2,
          data: 'Item 2'
        },
        {
          id: 3,
          data: 'Item 3'
        },
        {
          id: 4,
          data: 'Item 4'
        },
        {
          id: 5,
          data: 'Item 5'
        }
      ],
      events: [
        {
          title: 'All Day Event',
          start: '2018-09-01'
        },
        {
          title: 'Long Event',
          start: '2018-09-07',
          end: '2018-09-10'
        },
        {
          id: 999,
          title: 'Repeating Event',
          start: '2018-09-09T16:00:00'
        },
        {
          id: 999,
          title: 'Repeating Event',
          start: '2018-09-16T16:00:00'
        },
        {
          title: 'Conference',
          start: '2018-09-11',
          end: '2018-09-13'
        },
        {
          title: 'Meeting',
          start: '2018-09-12T10:30:00',
          end: '2018-09-12T12:30:00'
        },
        {
          title: 'Lunch',
          start: '2018-09-12T12:00:00'
        },
        {
          title: 'Meeting',
          start: '2018-09-12T14:30:00'
        },
        {
          title: 'Happy Hour',
          start: '2018-09-12T17:30:00'
        },
        {
          title: 'Dinner',
          start: '2018-09-12T20:00:00'
        },
        {
          title: 'Birthday Party',
          start: '2018-09-13T07:00:00'
        },
        {
          title: 'Click for Google',
          url: 'http://google.com/',
          start: '2018-09-28'
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  body {
    margin-top: 40px;
    text-align: center;
    font-size: 14px;
    font-family: "Lucida Grande",Helvetica,Arial,Verdana,sans-serif;
  }
  #wrap {
    width: 1100px;
    margin: 0 auto;
  }
  #external-events {
    float: right;
    width: 150px;
    padding: 0 10px;
    border: 1px solid #ccc;
    background: #eee;
    text-align: left;
  }
  #external-events h4 {
    font-size: 16px;
    margin-top: 0;
    padding-top: 1em;
  }
  #external-events .fc-event {
    margin: 10px 0;
    cursor: pointer;
  }
  #external-events p {
    margin: 1.5em 0;
    font-size: 11px;
    color: #666;
  }
  #external-events p input {
    margin: 0;
    vertical-align: middle;
  }
  #calendar {
    float: left;
    width: 900px;
  }
</style>
