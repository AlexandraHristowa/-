Namespace Events

    Using System;
Using System.Text;
        
Public Class Event : IComparable
{
	Public Event(DateTime, String title , String location ) 
        {
		this.date = date;
		
		this.title = title;
			this.location = location;
	}

	
        Public DateTime Date { Get; Set; }

        Public String Title { Get; Set; }

        Public String Location { Get; Set; }

    {
            Event other() = obj As Event;
            int byDate = this.Date.CompareTo(other.Date);
            int byTitle = this.Title.CompareTo(other.Title);
            int byLocation = this.Location.CompareTo(other.Location);

            If (byDate == 0)
            {
                If (byTitle == 0)
                {
                    Return byLocation;
                }
                Else
                {
                    Return byTitle;
                }
            }
            Else
            {
                Return byDate;
            }
        }


	Public override String ToString ( )
	{
		StringBuilder toString = New StringBuilder();
		toString.Append( date .ToString("yyyy-MM-ddTHH:mm:ss") );
			
			
		toString.Append(" | "+title);
	
		Return toString.ToString();
	}
}

Static StringBuilder output = New StringBuilder();

	Static Class Messages
	{
		Public Static void EventAdded()
		{ output.Append("Event added\n"); }
		Public Static void EventDeleted(int x)
		{
			If (x == 0) NoEventsFound();
			
			Else output.AppendFormat("{0} events deleted\n",x);
		}
		Public Static void NoEventsFound() { output.Append( "No events found\n" ); }
		Public Static void PrintEvent ( Event eventToPrint ) {
		
		
			If (eventToPrint! = null) {
				output.Append( eventToPrint+"\n");
			}
		}
	}
