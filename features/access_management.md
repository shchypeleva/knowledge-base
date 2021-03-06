# Access management
TokenD is based on a permissioned blockchain that limit the parties (it can be either another person or external service) who can read and mutate the ledger.

Therefore Tokend has pack of functionalities that will help you to distribute the rights. In order to use them, you need to be familiar with 2 our key entities: *account* and *signers*

### Account

Account is the central data structure in TokenD. Account is identified by a public key and is being stored in the ledger. Anything else in the ledger, (e.g assets, offers, KYC) is related to one or more accounts.

In TokenD, we differ common user accounts (see [their types](/tech/key_entities/accounts#account-type)) that can manage only themselves from the account that can manage the whole system ([master](/tech/key_entities/accounts#account-type) account). By being the owner of master account, you are allowed to perform a set of operations that will impact the system. (For example, you can set fees, review KYC requests, manage secondary markets etc.)

### Signers

You can share the control of the account with multiple parties, by adding them as a signer to your account. The main use case for this is that the system owner can easily share the admin policies with his employees or/and some external services (for example, to process deposits/withdrawals). It is possible by adding a signer to the master account and giving the signer the specified set of properties:

#### Public key
   
   *Public key* of the ed25519 key pair. Used as identifier of the signer. The secret seed from such keypair is owned only by the person/service who represents signer and is not available to the account owner.
   
#### Signer type 
  
  *Signer type* is summarized the list of [rights](/tech/key_entities/signer), each of them defines the set of operations signer can perform.
  
#### Identity 
   
   Two signatures created by two different signers with same identity are considered as one.
 
#### Weight 
   
   *Weight* is the access level of signer. It means that signer's weight, in order to perform the operation, must be higher than the operation level threshold.
