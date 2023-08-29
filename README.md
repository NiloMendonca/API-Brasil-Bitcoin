# API-Brasil-Bitcoin

Base URL: https://higher-solucoes-backend.herokuapp.com

## (POST) /brasilBitcoinAuth
body:
```
{
	"login": "login",
	"password": "pass"
}
```
return:
```
{
	"res": {
		"token_type": "bearer",
		"access_token": "dab659aff1268afb9fb3810ae29bc14afaa55bcc",
		"access_token_expires_at": "2023-08-29T19:57:23.469Z",
		"scope": [],
		"user": {
			"type": "client",
			"name": "adm-higher-brasil-bitcoin",
			"id": null,
			"grants": [],
			"client_id": "adm-higher-brasil-bitcoin"
		},
		"expires_in": 3599,
		"id_token": "eyJ1c2VyIjp7InR5cGUiOiJjbGllbnQiLCJuYW1lIjoiYWRtLWhpZ2hlci1icmFzaWwtYml0Y29pbiIsImlkIjpudWxsLCJncmFudHMiOltdLCJjbGllbnRfaWQiOiJhZG0taGlnaGVyLWJyYXNpbC1iaXRjb2luIn19"
	}
}
```

## (POST) /brasilBitcoinQuote

headers: 
```
	{
          token: 'access_token'
	}
```
body:

```
	{
	  "quotedAmount": 150,
	  "baseCurrencyIso": "BRL",
	  "quotedCurrencyIso": "USD"
	}
```

return:
```
	{
		"res": {
			"id": "7f44e0bf-ce7e-4936-bbf3-4646d03e8858",
			"direction": "OUTBOUND",
			"baseCurrencyIso": "BRL",
			"totalBaseAmount": 732.57,
			"quotedCurrencyIso": "USD",
			"quotedAmount": 150,
			"spread": 0.13,
			"exchangeRate": 4.8653167,
			"marketRate": 4.859,
			"purpose": "CRYPTO",
			"tax": 2.77,
			"settlementPeriodInDays": 0,
			"createdAt": "2023-08-29T18:58:50.854Z",
			"expiresIn": "2023-08-29T18:59:05.854Z"
		}
	}
```

## (POST) '/brasilBitcoinAcceptQuote'

headers: 
```
	{
          token: 'access_token'
	}
```
body: 
```
	{
	  "quoteId": "7f44e0bf-ce7e-4936-bbf3-4646d03e8858"
	}
```
return:
```
  {
    "id": "7788b9d1-ee63-4da3-b69f-65ac9d9aebdc",
    "externalId": "123123123",
    "quoteId": "11157e74-720d-4cc0-8383-dfe50f4459ec",
    "direction": "OUTBOUND",
    "baseCurrencyIso": "USD",
    "totalBaseAmount": 2000,
    "quotedCurrencyIso": "BRL",
    "quotedAmount": 396.26,
    "spread": 0.75,
    "exchangeRate": 5.0279999259,
    "purpose": "CRYPTO",
    "tax": 0.38,
    "sdkVersion": "2.0.0",
    "acceptedAt": "2022-06-12T21:51:07.296Z"
  }
```

## (POST) '/brasilBitcoinCreateTransaction'

headers: 
```
	{
          token: 'access_token'
	}
```
return:
```
  {
    "id": "d4905f3a-3346-4646-b91e-5380d8667ba8",
    "externalId": "3a484a4a",
    "direction": "OUTBOUND",
    "baseCurrencyIso": "USD",
    "totalBaseAmount": 604.5,
    "quotedCurrencyIso": "BRL",
    "totalQuotedAmount": 3051,
    "exchangeRate": 5.0279999258,
    "spread": 0.75,
    "purpose": "CRYPTO",
    "tax": 0.38,
    "marketRate": 5.085755668,
    "vet": 5.047146402,
    "status": "AWAITING_PAYMENT",
    "settlementPeriodInDays": 0,
    "createdAt": "2022-06-12T22:00:15.895Z"
  }
```

## (GET) /brasilBitcoinTransactions?initDate=10-10-2020&endDate=10-10-2023

headers: 
```
 {
          token: 'access_token'
	}
```
return:
```
  {
      "params": {
          "startDate": "2022-08-10",
          "endDate": "2022-08-10",
          "externalId": "cea33187-7da8-48c8-9ab6-a862e2772078",
      },
      "transactions": [
          {
              "id": "e6f1617c-328f-4c57-8f43-7653ec7b0f7c",
              "externalId": "cea33187-7da8-48c8-9ab6-a862e2772078",
              "counterpartyId": "1f3737c5-3b76-4761-b99c-8fdba694cfd3",
              "direction": "OUTBOUND",
              "baseCurrencyIso": "EUR",
              "totalBaseAmount": 5941.42,
              "quotedCurrencyIso": "BRL",
              "totalQuotedAmount": 31446.79,
              "exchangeRate": 5.2727694,
              "marketRate": 5.2154,
              "spread": 1.1,
              "purpose": "PAYMENT_PROCESSING",
              "tax": 0.38,
              "vet": 5.292807,
              "settlementPeriodInDays": 0,
              "createdAt": "2022-08-10T14:09:18.453Z",
              "status": "AWAITING_PAYMENT",
          }
      ],
      "currentPage": 1,
      "totalItems": 1,
      "pageSize": 100
  }
```

## (GET) '/brasilBitcoinQuotes'
*cotações criadas mas ainda não aceitas

headers: 
```
	{
          token: 'access_token'
	}
```

body: 
```
	{
	  "login": "29519837000123",
	  "password": "4$gt%12bHJ"
	}
```

return:
```
{
  "params": {
    "externalId": "cea33187-7da8-48c8-9ab6-a862e2772078",
    "hasTransaction": false
  },
  "quotes": [
    {
      "id": "997f475f-ad3e-4f1c-a6d4-cf794f8744cc",
      "externalId": "cea33187-7da8-48c8-9ab6-a862e2772078",
      "counterpartyId": "1f3737c5-3b76-4761-b99c-8fdba694cfd3",
      "quoteId": "caf6d456-8e66-4448-aaa1-f61bf685da24",
      "direction": "OUTBOUND",
      "baseCurrencyIso": "EUR",
      "totalBaseAmount": 5941.42,
      "quotedCurrencyIso": "BRL",
      "quotedAmount": 31444.35,
      "spread": 1.1,
      "exchangeRate": 5.272361457,
      "purpose": "PAYMENT_PROCESSING",
      "tax": 0.38,
      "sdkVersion": "",
      "acceptedAt": "2022-08-10T14:09:05.608Z"
    }
  ],
  "currentPage": 1,
  "totalItems": 1,
  "pageSize": 100
}
```

## (GET) '/brasilBitcoinOldQuotes'
*cotações criadas e aceitas

headers: 
```
 {
          token: 'access_token'
	}
```

return: 
```
{
  "params": {
    "externalId": "cea33187-7da8-48c8-9ab6-a862e2772078",
    "hasTransaction": false
  },
  "quotes": [
    {
      "id": "997f475f-ad3e-4f1c-a6d4-cf794f8744cc",
      "externalId": "cea33187-7da8-48c8-9ab6-a862e2772078",
      "counterpartyId": "1f3737c5-3b76-4761-b99c-8fdba694cfd3",
      "quoteId": "caf6d456-8e66-4448-aaa1-f61bf685da24",
      "direction": "OUTBOUND",
      "baseCurrencyIso": "EUR",
      "totalBaseAmount": 5941.42,
      "quotedCurrencyIso": "BRL",
      "quotedAmount": 31444.35,
      "spread": 1.1,
      "exchangeRate": 5.272361457,
      "purpose": "PAYMENT_PROCESSING",
      "tax": 0.38,
      "sdkVersion": "",
      "acceptedAt": "2022-08-10T14:09:05.608Z"
    }
  ],
  "currentPage": 1,
  "totalItems": 1,
  "pageSize": 100
}
```
