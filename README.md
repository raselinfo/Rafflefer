# Rafflefer

> This is the Raffle Draw application

## Project Requirements

### Client :

1. Make a application where people can buy one or multiple ticket at a time.
2. People can update their Profile
3. People can update their ticket name

### Admin:

1. Admin can also buy one or multiple ticket at a time.
2. Admin can create tickets
3. Admin can update ticket price ,name
4. Admin can draw the raffle and make one or more winners

## Models

### User :

- Name => String
- Email => String
- Password => String
- Created At => Date
- Updated At => Date

### Ticket

- Ticket ID => ID
- Price => Number
- USer ID => String (Not Required)
- IsSold => Boolean (Default = false)
- Created At => Date
- Updated At =>> Date

### Order

- Ticket => Object
- User => ID
- IsPaid => Boolean (Default = false)
- Created AT => Date

### Draw

- Winners => Array
- Created AT => Date
- Updated AT => Date

### DrawTime

- Limit => Number

## Routes

### Users

- /users/signup => Post (User)
- /users/signin => Post (User)
- /users/:userID => Patch (User / Admin)
- /users/:userID => Get (User / Admin)
- /users/:userName => Get (User / Admin)
- /user/:userID => Delete (Admin)

### Tickets

- /tickets/create => post (Admin)
- /tickets/bulk?cq=5 => post (Admin)
- /tickets/:ticketId => Patch (Admin)
- /tickets => Put (Admin)
- /tickets/:ticketId => Delete (Admin)
- /tickets => Delete (Admin)
- /tickets/id/:ticketId => Get (Admin)
- /tickets => Get (User / Admin)

### Purchase

- /tickets/order/ => Post (User)
- /tickets/order/ => Get (Admin)
- /tickets/order/id/:userID => Get (User / Admin)
- /tickets/order/id/:userID => Patch (User / Admin)
- /tickets/order/user/:userName => Get (Admin)
- /tickets/order => Delete (Admin)

### Draw

- /draw?wc=3 => Post (Admin)
- /draw/winners => Get (User / Admin)

### DrawLimit

- /drawlimit => Post (Admin)
