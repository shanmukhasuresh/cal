# cal
creating a calender
<link rel="stylesheet" href="dist/tui-calendar.css">
<script src="dist/tui-calendar.js"></script>
<div id="calendar"></div>
var Calendar = tui.Calendar;

var calendar = new Calendar('#calendar', {
    // options here
});
var calendar = new Calendar('#calendar', {

    // 'day', 'week', 'month'
    defaultView: 'week',

    // shows the milestone and task in weekly, daily view
    taskView: true,

    // shows the all day and time grid in weekly, daily view
    scheduleView: true,

    // override default styles here
    theme: {
      'common.border': '1px solid #e5e5e5',
      'common.backgroundColor': 'white',
      'common.holiday.color': '#ff4040',
      'common.saturday.color': '#333',
      'common.dayname.color': '#333',
      'common.today.color': '#333',

      // creation guide style
      'common.creationGuide.backgroundColor': 'rgba(81, 92, 230, 0.05)',
      'common.creationGuide.border': '1px solid #515ce6',

      // month header 'dayname'
      'month.dayname.height': '31px',
      'month.dayname.borderLeft': '1px solid #e5e5e5',
      'month.dayname.paddingLeft': '10px',
      'month.dayname.paddingRight': '10px',
      'month.dayname.backgroundColor': 'inherit',
      'month.dayname.fontSize': '12px',
      'month.dayname.fontWeight': 'normal',
      'month.dayname.textAlign': 'left',

      // month day grid cell 'day'
      'month.holidayExceptThisMonth.color': 'rgba(255, 64, 64, 0.4)',
      'month.dayExceptThisMonth.color': 'rgba(51, 51, 51, 0.4)',
      'month.weekend.backgroundColor': 'inherit',
      'month.day.fontSize': '14px',

      // month schedule style
      'month.schedule.borderRadius': '2px',
      'month.schedule.height': '24px',
      'month.schedule.marginTop': '2px',
      'month.schedule.marginLeft': '8px',
      'month.schedule.marginRight': '8px',

      // month more view
      'month.moreView.border': '1px solid #d5d5d5',
      'month.moreView.boxShadow': '0 2px 6px 0 rgba(0, 0, 0, 0.1)',
      'month.moreView.backgroundColor': 'white',
      'month.moreView.paddingBottom': '17px',
      'month.moreViewTitle.height': '44px',
      'month.moreViewTitle.marginBottom': '12px',
      'month.moreViewTitle.backgroundColor': 'inherit',
      'month.moreViewTitle.borderBottom': 'none',
      'month.moreViewTitle.padding': '12px 17px 0 17px',
      'month.moreViewList.padding': '0 17px',

      // week header 'dayname'
      'week.dayname.height': '42px',
      'week.dayname.borderTop': '1px solid #e5e5e5',
      'week.dayname.borderBottom': '1px solid #e5e5e5',
      'week.dayname.borderLeft': 'inherit',
      'week.dayname.paddingLeft': '0',
      'week.dayname.backgroundColor': 'inherit',
      'week.dayname.textAlign': 'left',
      'week.today.color': '#333',
      'week.pastDay.color': '#bbb',

      // week vertical panel 'vpanel'
      'week.vpanelSplitter.border': '1px solid #e5e5e5',
      'week.vpanelSplitter.height': '3px',

      // week daygrid 'daygrid'
      'week.daygrid.borderRight': '1px solid #e5e5e5',
      'week.daygrid.backgroundColor': 'inherit',

      'week.daygridLeft.width': '72px',
      'week.daygridLeft.backgroundColor': 'inherit',
      'week.daygridLeft.paddingRight': '8px',
      'week.daygridLeft.borderRight': '1px solid #e5e5e5',

      'week.today.backgroundColor': 'rgba(81, 92, 230, 0.05)',
      'week.weekend.backgroundColor': 'inherit',

      // week timegrid 'timegrid'
      'week.timegridLeft.width': '72px',
      'week.timegridLeft.backgroundColor': 'inherit',
      'week.timegridLeft.borderRight': '1px solid #e5e5e5',
      'week.timegridLeft.fontSize': '11px',
      'week.timegridLeftTimezoneLabel.height': '40px',
      'week.timegridLeftAdditionalTimezone.backgroundColor': 'white',

      'week.timegridOneHour.height': '52px',
      'week.timegridHalfHour.height': '26px',
      'week.timegridHalfHour.borderBottom': 'none',
      'week.timegridHorizontalLine.borderBottom': '1px solid #e5e5e5',

      'week.timegrid.paddingRight': '8px',
      'week.timegrid.borderRight': '1px solid #e5e5e5',
      'week.timegridSchedule.borderRadius': '2px',
      'week.timegridSchedule.paddingLeft': '2px',

      'week.currentTime.color': '#515ce6',
      'week.currentTime.fontSize': '11px',
      'week.currentTime.fontWeight': 'normal',

      'week.pastTime.color': '#bbb',
      'week.pastTime.fontWeight': 'normal',

      'week.futureTime.color': '#333',
      'week.futureTime.fontWeight': 'normal',

      'week.currentTimeLinePast.border': '1px dashed #515ce6',
      'week.currentTimeLineBullet.backgroundColor': '#515ce6',
      'week.currentTimeLineToday.border': '1px solid #515ce6',
      'week.currentTimeLineFuture.border': 'none',

      // week creation guide style
      'week.creationGuide.color': '#515ce6',
      'week.creationGuide.fontSize': '11px',
      'week.creationGuide.fontWeight': 'bold',

      // week daygrid schedule style
      'week.dayGridSchedule.borderRadius': '2px',
      'week.dayGridSchedule.height': '24px',
      'week.dayGridSchedule.marginTop': '2px',
      'week.dayGridSchedule.marginLeft': '8px',
      'week.dayGridSchedule.marginRight': '8px'
      }

    // template options
    template: {
      milestone: function(schedule) {
        return '&lt;span style="color:red;"&gt;&lt;i class="fa fa-flag"&gt;&lt;/i&gt; ' + schedule.title + '&lt;/span&gt;';
      },
      milestoneTitle: function() {
        return 'Milestone';
      },
      task: function(schedule) {
        return '&amp;nbsp;&amp;nbsp;#' + schedule.title;
      },
      taskTitle: function() {
        return '&lt;label&gt;&lt;input type="checkbox" /&gt;Task&lt;/label&gt;';
      },
      allday: function(schedule) {
        return schedule.title + ' &lt;i class="fa fa-refresh"&gt;&lt;/i&gt;';
      },
      alldayTitle: function() {
        return 'All Day';
      },
      time: function(schedule) {
        return schedule.title + ' &lt;i class="fa fa-refresh"&gt;&lt;/i&gt;' + schedule.start;
      }
    },

    // Options for daily, weekly view
    week: {
      daynames: ['Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat'],
      startDayOfWeek: 0,
      narrowWeekend: true,
      workweek: false,
      showTimezoneCollapseButton: false,
      timezonesCollapsed: false,
      hourStart: 0,
      hourEnd: 24,
    },

    // Options for monthly view.
    month: {
      daynames: ['Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat'],
      startDayOfWeek: 0,
      narrowWeekend: true,
      visibleWeeksCount: 6,
      isAlways6Week: true,
      workweek: false,
      visibleScheduleCount: 1,
      moreLayerSize: {},
      grid: {}, // grid's header and footer information
      scheduleFilter: null
    },

    // list of Calendars that can be used to add new schedule
    /* e.g.
      [
        {
          id: '1',
          name: 'My Calendar',
          color: '#ffffff',
          bgColor: '#9e5fff',
          dragBgColor: '#9e5fff',
          borderColor: '#9e5fff'
        },
        {
          id: '2',
          name: 'Company',
          color: '#00a9ff',
          bgColor: '#00a9ff',
          dragBgColor: '#00a9ff',
          borderColor: '#00a9ff'
        },
      ]
    */
    calendars: [],

    // whether use default creation popup or not
    useCreationPopup: false,

    // whether use default detail popup or not
    useDetailPopup: false,

    // timezone options
    timezone: {
      zones: [
        {
          timezoneName: 'Asia/Seoul',
          displayLabel: 'GMT+09:00',
          tooltip: 'Seoul'
        },
        {
          timezoneName: 'America/New_York',
          displayLabel: 'GMT-05:00',
          tooltip: 'New York',
        }
      ],
      offsetCalculator: function(timezoneName, timestamp){
        // matches 'getTimezoneOffset()' of Date API
        // e.g. +09:00 => -540, -04:00 => 240
        return moment.tz.zone(timezoneName).utcOffset(timestamp);
      },
    },

    // disable double click
    disableDblClick: false,

    // disble click
    disableClick: false,

    // is readonly?
    isReadOnly: false,

    // enable usage statistics
    usageStatistics: true
    
});
