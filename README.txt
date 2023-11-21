Communication Contract

How to request data : 
You'll need to create an event (for example a button) that triggers the data request to be activated. It can be done using a 
await/fetch approach using the POST method. The request that is being sent needs to be in the format of Json. The API is api/get-char.

ex. 
const response = await fetch("/get-char", {
    method: "POST",
    headers: {"Content-Type": "application/json"},
    body: JSON.stringify(selected_user)
});


How to receive data :

it needs to receive data by awaiting the promise that was created when the data was requested. The response will be in the format of Json : {type}.
ex.
const {type} = await response.json()

UML Diagram:

Program makes a request     |     get-char API          |          MicroScervice              

          sends name of the character        series of if statements to check which type the character belongs to   
          ---------------------------->          ---------------------------->

                Sends the type of Genshin Character information to the program
                <-------------------------------------------------------
                             
