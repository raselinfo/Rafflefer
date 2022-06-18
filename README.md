# Rafflefer

> This is the Raffle Draw application

## Project Requirements

### Client :

1. Make a application where people can buy one or multiple ticket at a time.
2. People can update their ticket name

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
- IsSold => Boolean
- Created At => Date
- Updated At =>> Date

### Purchases

- Ticket => Object
- User => ID
- IsPaid => Boolean
- Created AT => Date

### Draw

- Winners => Array
- Created AT => Date
- Updated AT => Date

### DrawTime

- Limit => number

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
- /tickets/:ticketId => Delete (Admin)
- /tickets => Delete (Admin)
- /tickets/id/:ticketId => Get (Admin)
- /tickets => Get (User / Admin)

### Purchase

- /tickets/purchase/ => Post (User)
- /tickets/purchase/ => Get (Admin)
- /tickets/purchase/id/:userID => Get (User / Admin)
- /tickets/purchase/user/:userName => Get (Admin)
- /tickets/purchase => Delete (Admin)

### Draw

- /draw?wc=3 => Post (Admin)
- /draw/winners => Get (User / Admin)
