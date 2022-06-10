+++
title = "Ethersjs Factories"
date = 2022-06-09
+++

Conectar

```typescript
export const useERC20 = (address: string) => {
  const { isAppConnected, readOnlyAppProvider, web3Provider } =
    useWeb3Connection();
  const provider =
    isAppConnected && web3Provider
      ? web3Provider.getSigner()
      : readOnlyAppProvider;

  return ERC20__factory.connect(address, provider);
};
```
