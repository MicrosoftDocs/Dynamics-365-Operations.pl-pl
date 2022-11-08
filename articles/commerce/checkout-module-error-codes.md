---
title: Kody odwołania błędów modułu wyewidencjonowania
description: W tym artykule opisano kody odwołań do błędów modułu realizacji zamówienia, które są pokazywane w komunikatach o błędach widocznych dla użytkownika w programie Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 10/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-09-20
ms.openlocfilehash: 952cb932522b4e0bb91be985e4f8974cb6cd8bc0
ms.sourcegitcommit: 435e69160dbd7f9c61b37ac4440285a5df144622
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2022
ms.locfileid: "9728253"
---
# <a name="checkout-module-error-reference-codes"></a>Kody odwołania błędów modułu wyewidencjonowania

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

W tym artykule opisano kody do błędów modułu realizacji zamówienia, które są pokazywane w komunikatach o błędach widocznych dla użytkownika w programie Microsoft Dynamics 365 Commerce.

Rozwiązanie Dynamics 365 Commerce wprowadziło standardowe odwołania do błędów, które można uwzględniać w błędach realizacji transakcji kanału online, wyświetlanych klientom w trybie online. W wersji Commerce 10.0.31 i nowszej komunikaty o błędach w module realizacji zawierają kody błędów i nie pokazują niepotrzebnych informacji odbiorcy w trybie online. Kody błędów odnoszą się do błędów, które są opisane szczegółowo w tym artykule.

W zależności od napotkanych błędów tabela w tym artykule zawiera następujące szczegóły:

- Opis warunku, który spowodował błąd, lub dodatkowe szczegóły
- Informacje do uwzględnienia w konfiguracjach środowiska lub łącznika płatności
- Informacje, do których można się odwoływać w sprawie obsługi, jeśli wymagana jest dodatkowa pomoc

## <a name="prerequisites"></a>Wymagania wstępne

Aby włączyć kody odwołań do błędów modułu wyewidencjonowania wymienione poniżej, w konstruktorze witryn dla witryny przejdź do **Ustawienia witryny \> Rozszerzenia**, a w sekcji **Karta i wyewidencjonowanie** wybierz **Włącz rozszerzone komunikaty wyświetlające błąd kanału w trybie online**. 

## <a name="checkout-module-error-reference-codes"></a>Kody odwołania błędów modułu wyewidencjonowania

W poniższej tabeli podano więcej szczegółów dotyczących odwołań do kodów błędów, które są dostarczane przez klientów lub zdarzyły się w sklepie internetowym. Przewiń w prawo, aby wyświetlić kolumnę **Opis błędu**.

| Kod błędu | Skorelowany kod błędu systemu Dynamics | Opis błędu |
| ---------- | ------------------------------ | ----------------- |
| CCR001     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToAuthorizePaymentCardTypeMissingOrNotSupported | Nie można autoryzować płatności. Brakuje identyfikatora typu karty w obszarze **TokenizedPaymentCard** lub podany identyfikator typu karty nie jest obsługiwany. |
| CCR002     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToAuthorizePayment | Odrzucono. Nie można autoryzować płatności. |
| CCR003     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToAuthorizePaymentCardAdditionalContextRequired | Nie można autoryzować płatności. Dodatkowe informacje wymagane od klienta. |
| CCR004     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToRetrieveCardPaymentAcceptResult | Przepraszamy, coś poszło nie tak. Nie można było uzyskać wyniku akceptacji płatności kartą. Spróbuj ponownie lub skontaktuj się z administratorem systemu. |
| CCR005     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentRequiresMerchantProperties | Nie można wykonać płatności z powodu braku właściwości płatności handlowca. Skontaktuj się z administratorem systemu. |
| CCR006     | Microsoft\_Dynamics\_Commerce\_Runtime\_InvalidPaymentRequest | Nie można pobrać usługi formy płatności dla operacji. Sprawdź ustawienia formy płatności dla wybranego typu formy płatności. |
| CCR007     | Microsoft\_Dynamics\_Commerce\_Runtime\_MultipleCustomerAccountPaymentsNotAllowed | Dokonano już wpłaty na konto odbiorcy, a można dokonać tylko jednej płatności na transakcję. |
| CCR008     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountLimitSignDifferentFromAmountDue | Limit konta odbiorcy różni się od należnej kwoty. Spróbuj użyć innej formy płatności lub skontaktuj się z pomocą techniczną klienta, aby uzyskać pomoc. |
| CCR009     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountPaymentExceedsTotalAmountForCarryOutAndReturnItems | Płatność na konto odbiorcy przekracza łączną kwotę należną dla wymienionych pozycji. Spróbuj ponownie później lub skontaktuj się z obsługą klienta, aby uzyskać dalszą pomoc. |
| CCR010     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentUsingUnauthorizedAccount | Płatność na konto odbiorcy wymaga osobnego konta lub pasującego konta płatnika w wierszu zapłaty. |
| CCR011     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountPaymentExceedsCustomerAccountFloorLimit | Nie można w tej chwili wykonać przetwarzania wpłaty na konto odbiorcy — przekroczono limit wydatków niewymagający autoryzacji. |
| CCR012     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountPaymentForCustomerWithoutAllowOnAccount | Ten odbiorca nie może zapłacić akonto. |
| CCR013     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToCancelPayment | Przepraszamy, coś poszło nie tak. Nie można anulować płatności. Spróbuj ponownie. |
| CCR014     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToReadCardTokenInfo | Wystąpił błąd w trakcie przetwarzania płatności. Spróbuj ponownie później. |
| CCR015     | Microsoft\_Dynamics\_Commerce\_Runtime\_NotEnoughRewardPoints | Kwota płatności w ramach programu lojalnościowego przekracza kwotę dozwoloną dla użytej karty lojalnościowej w tej transakcji. |
| CCR016     | Microsoft\_Dynamics\_Commerce\_Runtime\_RefundAmountMoreThanAllowed | Kwota zwrotu kosztów w ramach programu lojalnościowego przekracza kwotę dozwoloną dla użytej karty lojalnościowej w tej transakcji. |
| CCR017     | Microsoft\_Dynamics\_Commerce\_Runtime\_InvalidLoyaltyCardNumber | Nie znaleziono numeru karty lojalnościowej. Ajtywuj numer karty lojalnościowej lub wprowadź inny numer karty, a następnie spróbuj ponownie. |
| CCR018     | Microsoft\_Dynamics\_Commerce\_Runtime\_BlockedLoyaltyCard | Numer karty lojalnościowej nie jest dostępny. Wprowadź inny numer karty, a następnie spróbuj ponownie. |
| CCR019     | Microsoft\_Dynamics\_Commerce\_Runtime\_NoTenderLoyaltyCard | Ta karta lojalnościowa nie jest uprawniona do realizacji punktów lojalnościowych dla tej transakcji. |
| CCR020     | Microsoft\_Dynamics\_Commerce\_Runtime\_GiftCardCurrencyMismatch | Numer karty upominkowej napotkał błąd. Spróbuj użyć innej karty upominkowej lub skontaktuj się z pomocą techniczną klienta, aby uzyskać pomoc. |
| CCR021     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentAmountExceedsGiftBalance | Kwota przekracza saldo na karcie upominkowej. Wprowadź inną kwotę, a następnie spróbuj ponownie. |
| CCR022     | Microsoft\_Dynamics\_Commerce\_Runtime\_NoMoreThanOneLoyaltyTender | Transakcja może zawierać tylko jeden wiersz z płatnością w ramach programu lojalnościowego. |
| CCR023     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentAlreadyVoided | Brak informacji o płatności lub są one niepoprawne. Zweryfikuj informacje o płatności i spróbuj ponownie. |
| CCR024     | Microsoft\_Dynamics\_Commerce\_Runtime\_FraudRisk | Nie można teraz przetworzyć zamówienia. Spróbuj ponownie później. |
| CCR025     | Limit czasu frontonu dla interfejsu API realizacji transakcji | Upłynął czas operacji frontonu. Potwierdź, jeśli zamówienie zostało przetworzone w centrali Dynamics 365 Commerce headquarters. |
| CCR026     | Oryginalna autoryzowana kwota zmieniona | Kwota zamówienia zmieniła się z oryginalnej kwoty autoryzacji przetwarzanej za pomocą bramy płatności. Może to być spowodowane upływem terminu ważności kuponu, promocji lub sprzedaży. |
| CCR027     | Microsoft\_Dynamics\_Commerce\_Runtime\_InvalidCartVersion | Wystąpił błąd w trakcie przetwarzania płatności. Odwołanie dostarczone do interfejsu API koszyka ma inne odwołanie niż oczekiwane (ze względu na potencjalną niespójność w procesie realizacji zamówienia). |
| CCR028     | Microsoft\_Dynamics\_Commerce\_Runtime\_MissingRequiredCartTenderLines | W formie płatności wystąpił błąd. Skontaktuj się z pomocą techniczną, aby przejrzeć ustawienia konta, lub spróbuj ponownie z inną formą płatności. |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Płatności — często zadawane pytania](dev-itpro/payments-retail.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł płatności](payment-module.md)
