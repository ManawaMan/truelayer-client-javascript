# Classes

<dl>
<dt><a href="#AuthAPIClient">AuthAPIClient</a></dt>
<dd></dd>
<dt><a href="#DataAPIClient">DataAPIClient</a></dt>
<dd></dd>
</dl>

<a name="AuthAPIClient"></a>

# AuthAPIClient
This class is responsible for performing authentication with TrueLayer

* [AuthAPIClient](#AuthAPIClient)
    * [new AuthAPIClient()](#new_AuthAPIClient_new)
    * [new AuthAPIClient(options)](#new_AuthAPIClient_new)
    * [.getAuthUrl(config)](#AuthAPIClient+getAuthUrl) ⇒ <code>string</code>
    * [.exchangeCodeForToken(redirectURI, code)](#AuthAPIClient+exchangeCodeForToken) ⇒ <code>Promise.&lt;IToken&gt;</code>
    * [.refreshAccessToken(refreshToken)](#AuthAPIClient+refreshAccessToken) ⇒ <code>Promise.&lt;IToken&gt;</code>

<a name="new_AuthAPIClient_new"></a>

### new AuthAPIClient()
Class is responsible for performing authentication with TrueLayer

<a name="new_AuthAPIClient_new"></a>

### new AuthAPIClient(options)
Creates an instance of AuthAPIClient.
If no constructor options are passed then look for environment variables by default.


| Param | Type |
| --- | --- |
| options | <code>IOptions</code> | 

<a name="AuthAPIClient+getAuthUrl"></a>

### authAPIClient.getAuthUrl(config) ⇒ <code>string</code>
Builds a correctly formatted authentication url

**Kind**: instance method of [<code>AuthAPIClient</code>](#AuthAPIClient)  

| Param | Type |
| --- | --- |
| config | <code>IConfig</code> |

<a name="AuthAPIClient+exchangeCodeForToken"></a>

### authAPIClient.exchangeCodeForToken(redirectURI, code) ⇒ <code>Promise.&lt;IToken&gt;</code>
Exchanges an auth code for an access token

**Kind**: instance method of [<code>AuthAPIClient</code>](#AuthAPIClient)  

| Param | Type |
| --- | --- |
| redirectURI | <code>string</code> | 
| code | <code>string</code> | 

<a name="AuthAPIClient+refreshAccessToken"></a>

### authAPIClient.refreshAccessToken(refreshToken) ⇒ <code>Promise.&lt;IToken&gt;</code>
Exchanges a refresh token for a fresh access token

**Kind**: instance method of [<code>AuthAPIClient</code>](#AuthAPIClient)  

| Param | Type |
| --- | --- |
| refreshToken | <code>string</code> | 


<br/>
<br/>


<a name="DataAPIClient"></a>
# DataAPIClient
Class responsible for calling to the Data endpoints

* [DataAPIClient](#DataAPIClient)
    * [.callAPI(accessToken, path, [qs])](#DataAPIClient.callAPI) ⇒ <code>Promise.&lt;IResponse.&lt;T&gt;&gt;</code>
    * [.getMe(accessToken)](#DataAPIClient.getMe) ⇒ <code>Promise.&lt;IResponse.&lt;IMe&gt;&gt;</code>
    * [.getInfo(accessToken)](#DataAPIClient.getInfo) ⇒ <code>Promise.&lt;IResponse.&lt;IInfo&gt;&gt;</code>
    * [.getAccounts(accessToken)](#DataAPIClient.getAccounts) ⇒ <code>Promise.&lt;IResponse.&lt;IAccount&gt;&gt;</code>
    * [.getAccount(accessToken, accountId)](#DataAPIClient.getAccount) ⇒ <code>Promise.&lt;IResponse.&lt;IAccount&gt;&gt;</code>
    * [.getDirectDebits(accessToken, accountId)](#DataAPIClient.getDirectDebits) ⇒ <code>Promise.&lt;IResponse.&lt;IDirectDebit&gt;&gt;</code>
    * [.getStandingOrders(accessToken, accountId)](#DataAPIClient.getStandingOrders) ⇒ <code>Promise.&lt;IResponse.&lt;IStandingOrder&gt;&gt;</code>
    * [.getTransactions(accessToken, accountId, from, to)](#DataAPIClient.getTransactions) ⇒ <code>Promise.&lt;IResponse.&lt;ITransaction&gt;&gt;</code>
    * [.getBalance(accessToken, accountId)](#DataAPIClient.getBalance) ⇒ <code>Promise.&lt;IResponse.&lt;IBalance&gt;&gt;</code>
    * [.validateToken(accessToken)](#DataAPIClient.isTokenExpired) ⇒ <code>boolean</code>

<a name="DataAPIClient.callAPI"></a>

### DataAPIClient.callAPI(accessToken, path, [qs]) ⇒ <code>Promise.&lt;IResponse.&lt;T&gt;&gt;</code>
Generic API calling function

**Kind**: static method of [<code>DataAPIClient</code>](#DataAPIClient)  
**Template**: T  

| Param | Type |
| --- | --- |
| accessToken | <code>string</code> | 
| path | <code>string</code> | 
| [qs] | <code>object</code> | 

<a name="DataAPIClient.getMe"></a>

### DataAPIClient.getMe(accessToken) ⇒ <code>Promise.&lt;IResponse.&lt;IMe&gt;&gt;</code>
Call to /me API.

**Kind**: static method of [<code>DataAPIClient</code>](#DataAPIClient)  

| Param | Type |
| --- | --- |
| accessToken | <code>string</code> |

<a name="DataAPIClient.getInfo"></a>

### DataAPIClient.getInfo(accessToken) ⇒ <code>Promise.&lt;IResponse.&lt;IInfo&gt;&gt;</code>
Call to /info API.

**Kind**: static method of [<code>DataAPIClient</code>](#DataAPIClient)  

| Param | Type |
| --- | --- |
| accessToken | <code>string</code> | 

<a name="DataAPIClient.getAccounts"></a>

### DataAPIClient.getAccounts(accessToken) ⇒ <code>Promise.&lt;IResponse.&lt;IAccount&gt;&gt;</code>
Call to /accounts API.

**Kind**: static method of [<code>DataAPIClient</code>](#DataAPIClient)  

| Param | Type |
| --- | --- |
| accessToken | <code>string</code> | 

<a name="DataAPIClient.getAccount"></a>

### DataAPIClient.getAccount(accessToken, accountId) ⇒ <code>Promise.&lt;IResponse.&lt;IAccount&gt;&gt;</code>
Call to /accounts/account_id API.

**Kind**: static method of [<code>DataAPIClient</code>](#DataAPIClient)  

| Param | Type |
| --- | --- |
| accessToken | <code>string</code> | 
| accountId | <code>string</code> |

### DataAPIClient.getDirectDebits(accessToken, accountId) ⇒ <code>Promise.&lt;IResponse.&lt;IDirectDebit&gt;&gt;</code>
Call to /accounts/account_id/direct_debits API.

**Kind**: static method of [<code>DataAPIClient</code>](#DataAPIClient)  

| Param | Type |
| --- | --- |
| accessToken | <code>string</code> | 
| accountId | <code>string</code> |

### DataAPIClient.getStandingOrders(accessToken, accountId) ⇒ <code>Promise.&lt;IResponse.&lt;IStandingOrder&gt;&gt;</code>
Call to /accounts/account_id/standing_orders API.

**Kind**: static method of [<code>DataAPIClient</code>](#DataAPIClient)  

| Param | Type |
| --- | --- |
| accessToken | <code>string</code> | 
| accountId | <code>string</code> |

<a name="DataAPIClient.getTransactions"></a>

### DataAPIClient.getTransactions(accessToken, accountId, from, to) ⇒ <code>Promise.&lt;IResponse.&lt;ITransaction&gt;&gt;</code>
Call to /accounts/account_id/transactions API

Date format expected: YYYY-MM-DD

**Kind**: static method of [<code>DataAPIClient</code>](#DataAPIClient)  

| Param | Type |
| --- | --- |
| accessToken | <code>string</code> | 
| accountId | <code>string</code> |
| from | <code>string</code> format: YYYY-MM-DD |
| to | <code>string</code> format: YYYY-MM-DD |

<a name="DataAPIClient.getBalance"></a>

### DataAPIClient.getBalance(accessToken, accountId) ⇒ <code>Promise.&lt;IResponse.&lt;IBalance&gt;&gt;</code>
Call to /accounts/account_id/balance API

**Kind**: static method of [<code>DataAPIClient</code>](#DataAPIClient)  

| Param | Type |
| --- | --- |
| accessToken | <code>string</code> | 
| accountId | <code>string</code> |

<a name="DataAPIClient.isTokenExpired"></a>

### DataAPIClient.validateToken(accessToken) ⇒ <code>boolean</code>
Returns whether the token has expired or not

**Kind**: static method of [<code>DataAPIClient</code>](#DataAPIClient)  

| Param | Type |
| --- | --- |
| accessToken | <code>string</code> | 

