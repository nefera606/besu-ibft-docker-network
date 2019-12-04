# besu-ibft-docker-network
A dockerized network build with Hyperledger besu and IBFT consensus
```mermaid
sequenceDiagram
    CPR-->PaymentProcessor: startNewPayment(_bicccs, _marketMakers, _quoteClaims, _baseAmount, _desiredRates, _desiredFactors, _paymentData)
    PaymentProcessor-->Payment: constructor()
```
