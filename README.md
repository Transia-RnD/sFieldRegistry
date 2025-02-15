
# SFCode Registry Tables

## How to use

1. If you are working on an Amendment to the XRP Ledger (or a sidechain) and you need additional serialized fields then you should register them here to avoid clobbering others.
2. Register by opening a PR against this repo with your proposed registration as changes to the tables below. Provided the reservations are reasonable these will be accepted.
3. If your code is already in use then enter it into the `used by` column otherwise use the `reserved by` column. Be descriptive but terse in the `reserved by` field. Other developers should understand why this code is being reserved.

## Bump Script

You can use the bump script if you already have the definitions file or a rippled build. The script will merge your definition with this repo.

python3 bump.py | action | name | path

- `python3 bump.py definitions Hooks ./definitions.json`
- `python3 bump.py rippled Hooks ./rippled`

If you would like to know what sfields your rippled build is missing then run with:

- `DEBUG=True python3 bump.py definitions Hooks ./rippled`


## UINT16
Type 1

|Field Code|Field Name|Used by|Reserved by|
|-|-|-|-|
|1|LedgerEntryType|Ledger|n/a|
|2|TransactionType|Transaction|n/a|
|3|SignerWeight|Transaction|n/a|
|4|TransferFee|Transaction|n/a|
|5|TradingFee|XLS30|n/a|
|6|DiscountedFee|XLS30|n/a|
|16|Version|n/a|n/a|
|17|HookStateChangeCount|Hooks|n/a|
|18|HookEmitCount|Hooks|n/a|
|19|HookExecutionIndex|Hooks|n/a|
|20|HookApiVersion|Hooks|n/a|


## UINT32
Type 2

|Field Code|Field Name|Used by|Reserved by|
|-|-|-|-|
|1|NetworkID|NetworkID|n/a|
|2|Flags|Transaction|n/a|
|3|SourceTag|Transaction|n/a|
|4|Sequence|Transaction|n/a|
|5|PreviousTxnLgrSeq|Transaction|n/a|
|6|LedgerSequence|Transaction|n/a|
|7|CloseTime|Ledger|n/a|
|8|ParentCloseTime|Ledger|n/a|
|9|SigningTime|Transaction|n/a|
|10|Expiration|AccountSet|n/a|
|11|TransferRate|AccountSet|n/a|
|12|WalletSize|AccountSet|n/a|
|13|OwnerCount|AccountSet|n/a|
|14|DestinationTag|Payment|n/a|
|16|HighQualityIn|Trustlines|n/a|
|17|HighQualityOut|Trustlines|n/a|
|18|LowQualityIn|Trustlines|n/a|
|19|LowQualityOut|Trustlines|n/a|
|20|QualityIn|Trustlines|n/a|
|21|QualityOut|Trustlines|n/a|
|22|StampEscrow|legacy/unused|n/a|
|23|BondAmount|legacy/unused|n/a|
|24|LoadFee|Consensus|n/a|
|25|OfferSequence|OfferCreate|n/a|
|26|FirstLedgerSequence|negativeUNL|n/a|
|27|LastLedgerSequence|All Txns|n/a|
|28|TransactionIndex|Metadata|n/a|
|29|OperationLimit|legacy/unused|n/a|
|30|ReferenceFeeUnits|FeeSettings|n/a|
|31|ReserveBase|FeeSettings|n/a|
|32|ReserveIncrement|FeeSettings|n/a|
|33|SetFlag|AccountSet|n/a|
|34|ClearFlag|AccountSet|n/a|
|35|SignerQuorum|MultiSign|n/a|
|36|CancelAfter|Escrow, Paychan|n/a|
|37|FinishAfter|Escrow, Paychan|n/a|
|38|SignerListID|Multisign|n/a|
|39|SettleDelay|Paychans|n/a|
|40|TicketCount|Tickets|n/a|
|41|TicketSequence|Tickets|n/a|
|42|NFTokenTaxon|XLS20|n/a|
|43|MintedNFTokens|XLS20|n/a|
|44|BurnedNFTokens|XLS20|n/a|
|45|HookStateCount|Hooks|n/a|
|46|EmitGeneration|Hooks|n/a|
|47|LockCount|XLS34|n/a|
|48|VoteWeight|XLS30|n/a|
|50|FirstNFTokenSequence|XLS30|n/a|


## UINT64
Type 3

|Field Code|Field Name|Used by|Reserved by|
|-|-|-|-|
|1|IndexNext|Directories|n/a|
|2|IndexPrevious|Directories|n/a|
|3|BookNode|Orderbooks|n/a|
|4|OwnerNode|Directories|n/a|
|5|BaseFee|FeeSettings|n/a|
|6|ExchangeRate|Orderbooks|n/a|
|7|LowNode|Checks|n/a|
|8|HighNode|Checks|n/a|
|9|DestinationNode|Checks, Escrow, Paychan|n/a|
|10|Cookie|Validations|n/a|
|11|ServerVersion|Validations|n/a|
|12|NFTokenOfferNode|XLS20|n/a|
|13|EmitBurden|Hooks|n/a|
|16|HookOn|Hooks|n/a|
|17|HookInstructionCount|Hooks|n/a|
|18|HookReturnCode|Hooks|n/a|
|19|ReferenceCount|Hooks|n/a|
|20|XChainClaimID|XLS38|n/a|
|21|XChainAccountCreateCount|XLS38|n/a|
|22|XChainAccountClaimCount|XLS38|n/a|


## HASH128
Type 4

|Field Code|Field Name|Used by|Reserved by|
|-|-|-|-|
|1|EmailHash|AccountSet|n/a|


## HASH256
Type 5

|Field Code|Field Name|Used by|Reserved by|
|-|-|-|-|
|1|LedgerHash|Metadata|n/a|
|2|ParentHash|Metadata|n/a|
|3|TransactionHash|Metadata|n/a|
|4|AccountHash|AccountSet|n/a|
|5|PreviousTxnID|Various|n/a|
|6|LedgerIndex|Metadata|n/a|
|7|WalletLocator|AccountSet|n/a|
|8|RootIndex|Directories|n/a|
|9|AccountTxnID|Account Root|n/a|
|10|NFTokenID|XLS20|n/a|
|11|EmitParentTxnID|Hooks|n/a|
|12|EmitNonce|Hooks|n/a|
|13|EmitHookHash|Hooks|n/a|
|14|AMMID|XLS30|n/a|
|16|BookDirectory|Directories|n/a|
|17|InvoiceID|Payment, Check|n/a|
|18|Nickname|legacy/unused|n/a|
|19|Amendment|Consensus|n/a|
|20|HookOn|Hooks|n/a|
|21|Digest|XLS35|n/a|
|22|Channel|Paychan|n/a|
|23|ConsensusHash|Consensus|n/a|
|24|CheckID|Hooks|n/a|
|25|ValidatedHash|Consensus|n/a|
|26|PreviousPageMin|XLS20|n/a|
|27|NextPageMin|XLS20|n/a|
|28|NFTokenBuyOffer|XLS20|n/a|
|29|NFTokenSellOffer|XLS20|n/a|
|30|HookStateKey|Hooks|n/a|
|31|HookHash|Hooks|n/a|
|32|HookNamespace|Hooks|n/a|
|33|HookSetTxnID|Hooks|n/a|
|34|OfferID|Hooks|n/a|
|35|EscrowID|XLS35|n/a|
|36|URITokenID|XLS35|n/a|
|257|hash|legacy|n/a|
|258|index|legacy|n/a|


## AMOUNT
Type 6

|Field Code|Field Name|Used by|Reserved by|
|-|-|-|-|
|1|Amount|Payment, TrustSet|n/a|
|2|Balance|Account Root, Paychan|n/a|
|3|LimitAmount|TrustSet|n/a|
|4|TakerPays|OfferCreate|n/a|
|5|TakerGets|OfferCreate|n/a|
|6|LowLimit|TrustSet|n/a|
|7|HighLimit|TrustSet|n/a|
|8|Fee|All Txns|n/a|
|9|SendMax|Partial payments|n/a|
|10|DeliverMin|Partial payments|n/a|
|11|Amount2|XLS30|n/a|
|12|BidMin|XLS30|n/a|
|13|BidMax|XLS30|n/a|
|16|MinimumOffer|legacy/unused|n/a|
|17|RippleEscrow|legacy/unused|n/a|
|18|DeliveredAmount|Partial payments|n/a|
|19|NFTokenBrokerFee|XLS20|n/a|
|20|HookCallbackFee|Hooks|n/a|
|21|LockedBalance|XLS34|n/a|
|22|BaseFeeDrops|FeeSettings|n/a|
|23|ReserveBaseDrops|FeeSettings|n/a|
|24|ReserveIncrementDrops|FeeSettings|n/a|
|25|LPTokenOut|XLS30|n/a|
|26|LPTokenIn|XLS30|n/a|
|27|EPrice|XLS30|n/a|
|28|Price|XLS30|n/a|
|29|SignatureReward|XLS38|n/a|
|30|MinAccountCreateAmount|XLS38|n/a|
|31|LPTokenBalance|XLS30|n/a|
|258|taker_gets_funded|legacy|n/a|
|259|taker_pays_funded|legacy|n/a|


## BLOB
Type 7

|Field Code|Field Name|Used by|Reserved by|
|-|-|-|-|
|1|PublicKey|All Txns|n/a|
|2|MessageKey|AccountRoot|n/a|
|3|SigningPubKey|Transactions|n/a|
|4|TxnSignature|Transactions|n/a|
|5|URI|XLS20, XLS35|n/a|
|6|Signature|Validations|n/a|
|7|Domain|AccountRoot|n/a|
|8|FundCode|Legacy/unused|n/a|
|9|RemoveCode|Legacy/unused|n/a|
|10|ExpireCode|Legacy/unused|n/a|
|11|CreateCode|Hooks|n/a|
|12|MemoType|All Txns|n/a|
|13|MemoData|All Txns|n/a|
|14|MemoFormat|All Txns|n/a|
|16|Fulfillment|EscrowCreate|n/a|
|17|Condition|EscrowCreate|n/a|
|18|MasterSignature|ValidatorList|n/a|
|19|UNLModifyValidator|negativeUNL|n/a|
|20|ValidatorToDisable|negativeUNL|n/a|
|21|ValidatorToReEnable|negativeUNL|n/a|
|22|HookStateData|Hooks|n/a|
|23|HookReturnString|Hooks|n/a|
|24|HookParameterName|Hooks|n/a|
|25|HookParameterValue|Hooks|n/a|
|26|Blob|Hooks|n/a|


## ACCOUNTID
Type 8

|Field Code|Field Name|Used by|Reserved by|
|-|-|-|-|
|1|Account|Various|n/a|
|2|Owner|XLS20|n/a|
|3|Destination|Payment|n/a|
|4|Issuer|TrustSet|n/a|
|5|Authorize|AccountSet|n/a|
|6|Unauthorize|AccountSet|n/a|
|8|RegularKey|AccountSet|n/a|
|9|NFTokenMinter|XLS20|n/a|
|10|EmitCallback|Hooks|n/a|
|11|AMMAccount|XLS30|n/a|
|16|HookAccount|Hooks|n/a|
|18|OtherChainSource|XLS38|n/a|
|19|OtherChainDestination|XLS38|n/a|
|20|AttestationSignerAccount|XLS38|n/a|
|21|AttestationRewardAccount|XLS38|n/a|
|22|LockingChainDoor|XLS38|n/a|
|23|IssuingChainDoor|XLS38|n/a|


## STOBJECT
Type 14

|Field Code|Field Name|Used by|Reserved by|
|-|-|-|-|
|1|ObjectEndMarker|Objects|n/a|
|2|TransactionMetaData|Metadata|n/a|
|3|CreatedNode|Metadata|n/a|
|4|DeletedNode|Metadata|n/a|
|5|ModifiedNode|Metadata|n/a|
|6|PreviousFields|Metadata|n/a|
|7|FinalFields|Metadata|n/a|
|8|NewFields|Metadata|n/a|
|9|TemplateEntry|unused/legacy|n/a|
|10|Memo|All Txn|n/a|
|11|SignerEntry|Multisign|n/a|
|12|NFToken|XLS20|n/a|
|13|EmitDetails|Hooks|n/a|
|14|Hook|Hooks|n/a|
|16|Signer|Multisign|n/a|
|18|Majority|Consensus|n/a|
|19|DisabledValidator|negativeUNL|n/a|
|20|EmittedTxn|Hooks|n/a|
|21|HookExecution|Hooks|n/a|
|22|HookDefinition|Hooks|n/a|
|23|HookParameter|Hooks|n/a|
|24|HookGrant|Hooks|n/a|
|25|VoteEntry|XLS30|n/a|
|26|AuctionSlot|XLS30|n/a|
|27|AuthAccount|XLS30|n/a|
|28|XChainClaimProofSig|XLS38|n/a|
|29|XChainCreateAccountProofSig|XLS38|n/a|
|30|XChainClaimAttestationBatchElement|XLS38|n/a|
|31|XChainCreateAccountAttestationBatchElement|XLS38|n/a|
|32|XChainClaimProofSig|XLS30|n/a|
|33|XChainCreateAccountProofSig|XLS30|n/a|
|34|XChainClaimAttestationCollectionElement|XLS30|n/a|
|35|XChainCreateAccountAttestationCollectionElement|XLS30|n/a|


## STARRAY
Type 15

|Field Code|Field Name|Used by|Reserved by|
|-|-|-|-|
|1|ArrayEndMarker|Arrays|n/a|
|3|Signers|Multisign|n/a|
|4|SignerEntries|Multisign|n/a|
|5|Template|Templating|n/a|
|6|Necessary|legacy/unused|n/a|
|7|Sufficient|legacy/unused|n/a|
|8|AffectedNodes|Metadata|n/a|
|9|Memos|All Txn|n/a|
|10|NFTokens|XLS20|n/a|
|11|Hooks|Hooks|n/a|
|12|VoteSlots|XLS30|n/a|
|16|Majorities|Consensus|n/a|
|17|DisabledValidators|negativeUNL|n/a|
|18|HookExecutions|Hooks|n/a|
|19|HookParameters|Hooks|n/a|
|20|HookGrants|Hooks|n/a|
|21|AuthAccounts|XLS30|n/a|
|22|XChainClaimAttestations|XLS38|n/a|
|23|XChainCreateAccountAttestations|XLS38|n/a|


## UINT8
Type 16

|Field Code|Field Name|Used by|Reserved by|
|-|-|-|-|
|1|CloseResolution|Consensus|n/a|
|2|Method|legacy/unused|n/a|
|3|TransactionResult|Metadata|n/a|
|16|TickSize|Orderbooks|n/a|
|17|UNLModifyDisabling|negativeUNL|n/a|
|18|HookResult|Hooks|n/a|
|19|WasLockingChainSend|XLS38|n/a|


## HASH160
Type 17

|Field Code|Field Name|Used by|Reserved by|
|-|-|-|-|
|1|TakerPaysCurrency|Offer|n/a|
|2|TakerPaysIssuer|Offer|n/a|
|3|TakerGetsCurrency|Offer|n/a|
|4|TakerGetsIssuer|Offer|n/a|


## PATHSET
Type 18

|Field Code|Field Name|Used by|Reserved by|
|-|-|-|-|
|1|Paths|Pathing|n/a|


## VECTOR256
Type 19

|Field Code|Field Name|Used by|Reserved by|
|-|-|-|-|
|1|Indexes|Ledger|n/a|
|2|Hashes|Ledger|n/a|
|3|Amendments|Ledger|n/a|
|4|NFTokenOffers|XLS20|n/a|
|5|HookNamespaces|Hooks|n/a|


## ISSUE
Type 24

|Field Code|Field Name|Used by|Reserved by|
|-|-|-|-|
|1|LockingChainIssue|XLS38|n/a|
|2|IssuingChainIssue|XLS38|n/a|
|3|Asset|XLS30|n/a|
|4|Asset2|XLS30|n/a|


## XCHAINBRIDGE
Type 25

|Field Code|Field Name|Used by|Reserved by|
|-|-|-|-|
|1|XChainBridge|XLS38|n/a|


## TRANSACTION RESULTS


|Response Code|Response Name|Used by|Reserved by|
|-|-|-|-|
|-399|telLOCAL_ERROR|legacy|n/a|
|-398|telBAD_DOMAIN|legacy|n/a|
|-397|telBAD_PATH_COUNT|legacy|n/a|
|-396|telBAD_PUBLIC_KEY|legacy|n/a|
|-395|telFAILED_PROCESSING|legacy|n/a|
|-394|telINSUF_FEE_P|legacy|n/a|
|-393|telNO_DST_PARTIAL|legacy|n/a|
|-392|telCAN_NOT_QUEUE|legacy|n/a|
|-391|telCAN_NOT_QUEUE_BALANCE|legacy|n/a|
|-390|telCAN_NOT_QUEUE_BLOCKS|legacy|n/a|
|-389|telCAN_NOT_QUEUE_BLOCKED|legacy|n/a|
|-388|telCAN_NOT_QUEUE_FEE|legacy|n/a|
|-387|telCAN_NOT_QUEUE_FULL|legacy|n/a|
|-386|telWRONG_NETWORK|NetworkID|n/a|
|-385|telREQUIRES_NETWORK_ID|NetworkID|n/a|
|-384|telNETWORK_ID_MAKES_TX_NON_CANONICAL|NetworkID|n/a|
|-383|telNON_LOCAL_EMITTED_TXN|Hooks|n/a|
|-299|temMALFORMED|legacy|n/a|
|-298|temBAD_AMOUNT|legacy|n/a|
|-297|temBAD_CURRENCY|legacy|n/a|
|-296|temBAD_EXPIRATION|legacy|n/a|
|-295|temBAD_FEE|legacy|n/a|
|-294|temBAD_ISSUER|legacy|n/a|
|-293|temBAD_LIMIT|legacy|n/a|
|-292|temBAD_OFFER|legacy|n/a|
|-291|temBAD_PATH|legacy|n/a|
|-290|temBAD_PATH_LOOP|legacy|n/a|
|-289|temBAD_REGKEY|legacy|n/a|
|-288|temBAD_SEND_XRP_LIMIT|legacy|n/a|
|-287|temBAD_SEND_XRP_MAX|legacy|n/a|
|-286|temBAD_SEND_XRP_NO_DIRECT|legacy|n/a|
|-285|temBAD_SEND_XRP_PARTIAL|legacy|n/a|
|-284|temBAD_SEND_XRP_PATHS|legacy|n/a|
|-283|temBAD_SEQUENCE|legacy|n/a|
|-282|temBAD_SIGNATURE|legacy|n/a|
|-281|temBAD_SRC_ACCOUNT|legacy|n/a|
|-280|temBAD_TRANSFER_RATE|legacy|n/a|
|-279|temDST_IS_SRC|legacy|n/a|
|-278|temDST_NEEDED|legacy|n/a|
|-277|temINVALID|legacy|n/a|
|-276|temINVALID_FLAG|legacy|n/a|
|-275|temREDUNDANT|legacy|n/a|
|-274|temRIPPLE_EMPTY|legacy|n/a|
|-273|temDISABLED|legacy|n/a|
|-272|temBAD_SIGNER|legacy|n/a|
|-271|temBAD_QUORUM|legacy|n/a|
|-270|temBAD_WEIGHT|legacy|n/a|
|-269|temBAD_TICK_SIZE|legacy|n/a|
|-268|temINVALID_ACCOUNT_ID|legacy|n/a|
|-267|temCANNOT_PREAUTH_SELF|legacy|n/a|
|-266|temINVALID_COUNT|legacy|n/a|
|-265|temUNCERTAIN|legacy|n/a|
|-264|temUNKNOWN|legacy|n/a|
|-263|temSEQ_AND_TICKET|legacy|n/a|
|-262|temBAD_NFTOKEN_TRANSFER_FEE|XLS20|n/a|
|-261|temAMM_BAD_TOKENS|XLS30|n/a|
|-260|temXCHAIN_EQUAL_DOOR_ACCOUNTS|XLS38|n/a|
|-259|temXCHAIN_BAD_PROOF|XLS38|n/a|
|-258|temXCHAIN_BRIDGE_BAD_ISSUES|XLS38|n/a|
|-257|temXCHAIN_BRIDGE_NONDOOR_OWNER|XLS38|n/a|
|-256|temXCHAIN_BRIDGE_BAD_MIN_ACCOUNT_CREATE_AMOUNT|XLS38|n/a|
|-255|temXCHAIN_BRIDGE_BAD_REWARD_AMOUNT|XLS38|n/a|
|-254|temXCHAIN_TOO_MANY_ATTESTATIONS|XLS38|n/a|
|-253|temHOOK_DATA_TOO_LARGE|Hooks|n/a|
|-252|temHOOK_REJECTED|Hooks|n/a|
|-199|tefFAILURE|legacy|n/a|
|-198|tefALREADY|legacy|n/a|
|-197|tefBAD_ADD_AUTH|legacy|n/a|
|-196|tefBAD_AUTH|legacy|n/a|
|-195|tefBAD_LEDGER|legacy|n/a|
|-194|tefCREATED|legacy|n/a|
|-193|tefEXCEPTION|legacy|n/a|
|-192|tefINTERNAL|legacy|n/a|
|-191|tefNO_AUTH_REQUIRED|legacy|n/a|
|-190|tefPAST_SEQ|legacy|n/a|
|-189|tefWRONG_PRIOR|legacy|n/a|
|-188|tefMASTER_DISABLED|legacy|n/a|
|-187|tefMAX_LEDGER|legacy|n/a|
|-186|tefBAD_SIGNATURE|legacy|n/a|
|-185|tefBAD_QUORUM|legacy|n/a|
|-184|tefNOT_MULTI_SIGNING|legacy|n/a|
|-183|tefBAD_AUTH_MASTER|legacy|n/a|
|-182|tefINVARIANT_FAILED|legacy|n/a|
|-181|tefTOO_BIG|legacy|n/a|
|-180|tefNO_TICKET|Tickets|n/a|
|-179|tefNFTOKEN_IS_NOT_TRANSFERABLE|XLS20|n/a|
|-99|terRETRY|legacy|n/a|
|-98|terFUNDS_SPENT|legacy|n/a|
|-97|terINSUF_FEE_B|legacy|n/a|
|-96|terNO_ACCOUNT|legacy|n/a|
|-95|terNO_AUTH|legacy|n/a|
|-94|terNO_LINE|legacy|n/a|
|-93|terOWNERS|legacy|n/a|
|-92|terPRE_SEQ|legacy|n/a|
|-91|terLAST|legacy|n/a|
|-90|terNO_RIPPLE|legacy|n/a|
|-89|terQUEUED|legacy|n/a|
|-88|terPRE_TICKET|Tickets|n/a|
|-87|terNO_AMM|XLS30|n/a|
|-86|terNO_HOOK|Hooks|n/a|
|0|tesSUCCESS|legacy|n/a|
|100|tecCLAIM|legacy|n/a|
|101|tecPATH_PARTIAL|legacy|n/a|
|102|tecUNFUNDED_ADD|legacy|n/a|
|103|tecUNFUNDED_OFFER|legacy|n/a|
|104|tecUNFUNDED_PAYMENT|legacy|n/a|
|105|tecFAILED_PROCESSING|legacy|n/a|
|121|tecDIR_FULL|legacy|n/a|
|122|tecINSUF_RESERVE_LINE|legacy|n/a|
|123|tecINSUF_RESERVE_OFFER|legacy|n/a|
|124|tecNO_DST|legacy|n/a|
|125|tecNO_DST_INSUF_XRP|legacy|n/a|
|126|tecNO_LINE_INSUF_RESERVE|legacy|n/a|
|127|tecNO_LINE_REDUNDANT|legacy|n/a|
|128|tecPATH_DRY|legacy|n/a|
|129|tecUNFUNDED|legacy|n/a|
|130|tecNO_ALTERNATIVE_KEY|legacy|n/a|
|131|tecNO_REGULAR_KEY|legacy|n/a|
|132|tecOWNERS|legacy|n/a|
|133|tecNO_ISSUER|legacy|n/a|
|134|tecNO_AUTH|legacy|n/a|
|135|tecNO_LINE|legacy|n/a|
|136|tecINSUFF_FEE|legacy|n/a|
|137|tecFROZEN|legacy|n/a|
|138|tecNO_TARGET|legacy|n/a|
|139|tecNO_PERMISSION|legacy|n/a|
|140|tecNO_ENTRY|legacy|n/a|
|141|tecINSUFFICIENT_RESERVE|legacy|n/a|
|142|tecNEED_MASTER_KEY|legacy|n/a|
|143|tecDST_TAG_NEEDED|legacy|n/a|
|144|tecINTERNAL|legacy|n/a|
|145|tecOVERSIZE|legacy|n/a|
|146|tecCRYPTOCONDITION_ERROR|legacy|n/a|
|147|tecINVARIANT_FAILED|legacy|n/a|
|148|tecEXPIRED|legacy|n/a|
|149|tecDUPLICATE|legacy|n/a|
|150|tecKILLED|legacy|n/a|
|151|tecHAS_OBLIGATIONS|legacy|n/a|
|152|tecTOO_SOON|legacy|n/a|
|153|tecHOOK_REJECTED|Hooks|n/a|
|154|tecMAX_SEQUENCE_REACHED|legacy|n/a|
|155|tecNO_SUITABLE_NFTOKEN_PAGE|XLS20|n/a|
|156|tecNFTOKEN_BUY_SELL_MISMATCH|XLS20|n/a|
|157|tecNFTOKEN_OFFER_TYPE_MISMATCH|XLS20|n/a|
|158|tecCANT_ACCEPT_OWN_NFTOKEN_OFFER|XLS20|n/a|
|159|tecINSUFFICIENT_FUNDS|legacy|n/a|
|160|tecOBJECT_NOT_FOUND|legacy|n/a|
|161|tecINSUFFICIENT_PAYMENT|legacy|n/a|
|162|tecAMM_UNFUNDED|XLS30|n/a|
|163|tecAMM_BALANCE|XLS30|n/a|
|164|tecAMM_FAILED_DEPOSIT|XLS30|n/a|
|165|tecAMM_FAILED_WITHDRAW|XLS30|n/a|
|166|tecAMM_INVALID_TOKENS|XLS30|n/a|
|167|tecAMM_FAILED_BID|XLS30|n/a|
|168|tecAMM_FAILED_VOTE|XLS30|n/a|
|169|tecXCHAIN_BAD_TRANSFER_ISSUE|XLS38|n/a|
|170|tecXCHAIN_NO_CLAIM_ID|XLS38|n/a|
|171|tecXCHAIN_BAD_CLAIM_ID|XLS38|n/a|
|172|tecXCHAIN_CLAIM_NO_QUORUM|XLS38|n/a|
|173|tecXCHAIN_PROOF_UNKNOWN_KEY|XLS38|n/a|
|174|tecXCHAIN_CREATE_ACCOUNT_NONXRP_ISSUE|XLS38|n/a|
|175|tecXCHAIN_WRONG_CHAIN|XLS38|n/a|
|176|tecXCHAIN_REWARD_MISMATCH|XLS38|n/a|
|177|tecXCHAIN_NO_SIGNERS_LIST|XLS38|n/a|
|178|tecXCHAIN_SENDING_ACCOUNT_MISMATCH|XLS38|n/a|
|179|tecXCHAIN_INSUFF_CREATE_AMOUNT|XLS38|n/a|
|180|tecXCHAIN_ACCOUNT_CREATE_PAST|XLS38|n/a|
|181|tecXCHAIN_ACCOUNT_CREATE_TOO_MANY|XLS38|n/a|
|182|tecXCHAIN_PAYMENT_FAILED|XLS38|n/a|
|183|tecXCHAIN_SELF_COMMIT|XLS38|n/a|
|184|tecXCHAIN_BAD_PUBLIC_KEY_ACCOUNT_PAIR|XLS38|n/a|
|185|tecXCHAIN_CREATE_ACCOUNT_DISABLED|XLS30|n/a|


