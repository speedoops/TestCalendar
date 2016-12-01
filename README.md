# TestCalendar
Insert new event into calendar programmatically

%%

If you want the user to be asked in which calendar to put the event.
Check http://stackoverflow.com/questions/3721963/how-to-add-calendar-events-in-android with the solution by oriharel. 

Calendar cal = Calendar.getInstance();              
Intent intent = new Intent(Intent.ACTION_EDIT);
intent.setType("vnd.android.cursor.item/event");  //should change to: .setData(CalendarContract.Events.CONTENT_URI)
intent.putExtra("beginTime", cal.getTimeInMillis());
intent.putExtra("allDay", true);
intent.putExtra("rrule", "FREQ=YEARLY");
intent.putExtra("endTime", cal.getTimeInMillis()+60*60*1000);
intent.putExtra("title", "A Test Event from android app");
startActivity(intent);
