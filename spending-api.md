# Spending API

Download spending transactions, categorising. View transactions over the year. Answering interesting questions like which supermarkets have I been spending in and how much.

## Transactions

```
GET /transactions?financialYear=2022&category=supermarket&name=*countdown*&skip=100&limit=100

[
    { 
        id: 12346,
        name: Countdown Linfield,
        value: -143.55,
        category: Supermarket,
        date: 3/6/2022,
        isExpense: true
    },
    { 
        id: 12345,
        name: Pak n Save Lincoln Road,
        value: -243.55,
        category: Supermarket,
        date: 2/6/2022,
        isExpense: true
    },
    { 
        id: 12345,
        name: Payment from Bob,
        value: 500.00,
        category: Income,
        date: 1/6/2022,
        isExpense: false
    }
]

GET /transactions/12346

{ 
    id: 12346,
    name: Countdown Linfield,
    value: 143.55,
    category: Supermarket,
    date: 3/6/2022
}

PUT /transactions/12346
Content-Type: application/json

{ 
    id: 12346,
    name: Countdown Linfield,
    value: 143.55,
    category: Leisure,
    date: 3/6/2022
}

PUT /transactions
Content-Type: application/json

[
    { 
        id: 12346,
        name: Countdown Linfield,
        value: -143.55,
        category: Leisure time,
        date: 3/6/2022,
        isExpense: true
    },
    { 
        id: 12345,
        name: Pak n Save Lincoln Road,
        value: -243.55,
        category: Leisure time,
        date: 2/6/2022,
        isExpense: true
    },
    ...
]



PATCH /transactions/12346

{ 
    category: Leisure
}

PATCH /transactions
Content-Type: application/json

[
    { 
        id: 12346,
        category: Leisure time
    },
    { 
        id: 12345,
        category: Leisure time
    },
    ...
]


DELETE /transactions/12346


POST /transactions
Content-Type: text/csv

12345,Coutndown,Blah,55.33
12345,Coutndown,Blah,55.33
12345,Coutndown,Blah,55.33
12345,Coutndown,Blah,55.33
12345,Coutndown,Blah,55.33
12345,Coutndown,Blah,55.33
```