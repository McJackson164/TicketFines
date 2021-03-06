## Functionality

This plugin makes it possible to issue tickets and impose fines. It's great for roleplay servers!

## Permissions

- `ticketfines.issue` --You can issue tickets to players.
- `ticketfines.demand` -- You can demand the payment of a ticket.
- `ticketfines.close` -- You can close tickets.
- `ticketfines.edit` -- You can edit the fine or the note of a ticket.

## Commands

- `fine` -- Shows all possible commands.
- `fine list` -- List all your unpaid tickets.
- `fine list <playerName>` -- List all unpaid tickets of given player (requires permission `ticketfines.demand`, `ticketfines.close` or `ticketfines.edit`).
- `fine pay <ticketID>` -- Pays the fine of the ticket with given ID. You can only pay your own tickets.
- `fine issue <playerName> <fine> <optional:note>` -- Issues a ticket to given player. You can add a note if you want. Fine can be 0.
- `fine demand <ticketID>` -- Demands the payment of the ticket with given ID. The player who got the ticket, has to be within the range, defined in the config.
- `fine close <ticketID>` -- Closes the ticket with given ID.
- `fine edit <ticketID> <field> <newValue>` -- Sets the field of ticket with given ID to newValue. Possible fields are `FINE` and `NOTE`.

## Configuration

```json
{
  "Enable fines (requires Economics OR Server Rewards OR custom currency item)": true,
  "Use 'Economics' plugin for payment (requires Economics)": false,
  "Use 'Server Rewards' plugin for payment (requires Server Rewards)": false,
  "Use custom currency for payment": true,
  "Custom Currency Item (requires 'Use custom currency' to be true. Use item shortname)": "scrap",
  "Enable automatic withdraw of fines (requires 'Enable fines' to be true)": false,
  "The demandent will receive a paid fine. (if false, the fine amount will be deleted)": true,
  "Maximum fine per ticket (default 1000.0)": 1000.0,
  "Currency (requires 'Use custom currency' to be true)": "Scrap",
  "Enable notes (descriptive note attached to a ticket)": true,
  "Tickets require note (tickets won't be issued without a note)": false,
  "Maximum note length (0 = unlimited)": 200,
  "Maximum distance in which you are able to demand a ticket (0 = unlimited)": 20
}
```

## Example Usage

- `/fine issue McJackson164 1337 "Grand Theft Auto"` -- Issues a ticket to `McJackson164` with a fine of `1337` and the note `Grand Theft Auto`.
- `/fine list McJackson164` -- Lists all unpaid tickets of player `McJackson164`.

## Changelog

### v1.1.4
- The issue and close date of a ticket will be saved and shown.

### v1.1.3
- Paid fines get transfered to the issuer/demandant of the ticket.

### v1.1.2
- Target receives an actual ticket as a note.

### v1.1.1
- Target receives a notification, if a ticket is issued.

### v1.1.0
- Limit the output of `/fine list` to 10.

### v1.0.0
- Initial release