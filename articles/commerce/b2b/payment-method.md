---
title: Konfigurowanie form płatności na konto klienta dla witryn handlu elektronicznego B2B
description: W tym artykule opisano sposób konfigurowania metody płatności konta odbiorcy w programie Microsoft Dynamics 365 Commerce. Opisano w nim także wpływ limitów kredytowych na rejestrowanie płatności a konta w witrynach e-commerce (B2B) firmy.
author: josaw1
ms.date: 04/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 20af517b9a69f4fb490d4d93ada8bc4063e895dd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878654"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a>Konfigurowanie form płatności na konto klienta dla witryn handlu elektronicznego B2B

[!include [banner](../../includes/banner.md)]

W tym artykule opisano sposób konfigurowania metody płatności konta odbiorcy w programie Microsoft Dynamics 365 Commerce. Opisano w nim także wpływ limitów kredytowych na rejestrowanie płatności a konta w witrynach e-commerce (B2B) firmy.

Sprzadawcy detaliczni mogą akceptować różne typy płatności w zamian za produkty i usługi, które sprzedają w kanale handlu elektronicznego. Każdy typ płatności akceptowany przez sprzedawcę detalicznego musi zostać skonfigurowany w Dynamics 365 Commerce na etapie konfiguracji systemu. W witrynach B2B handlu elektronicznego musi być obsługiwana metoda płatności konto odbiorcy (lub metoda płatności na konto). 

## <a name="prerequisites"></a>Wymagania wstępne

1. Dodaj metodę płatności konta odbiorcy w Commerce Headquarters.
2. Skojarz metodę płatności konta odbiorcy z kanałem handlu elektronicznego.
3. Upewnij się, że opcja **Zezwalaj na akonto** jest włączona dla odbiorcy w **Retail i Commerce \> Odbiorcy \> Wszyscy odbiorcy \> Ustawienia domyślne płatności** w Commerce Headquarters.

    > [!NOTE]
    > Jeśli wszyscy odbiorcy powinni mieć dostęp do włączonej metody płatności a koncie, dla domyślnego odbiorcy kanału skojarzonego z witryną B2B można ustawić wartość **Tak** dla właściwości **Zezwalaj a koncie**. 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a>Włącz metodę płatności na koncie klienta w narzędziu do tworzenia witryn Commerce 

Aby włączyć metodę płatności dla konta klienta w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.

1. Przejdź do **Ustawień witryny \> Rozszerzenia**.
1. Ustaw właściwość **Włącz płatności konta odbiorcy** na **Włącz dla odbiorców B2B**. 
1. Wybierz **Zapisz i opublikuj**.

> [!NOTE]
> Nowe ustawienia witryny zostaną wprowadzone dopiero po zaktualizowaniu pliku app.settings.json. Aby uzyskać więcej informacji, zobacz [Aktualizacje zestawu SDK i biblioteki modułów](../e-commerce-extensibility/sdk-updates.md).

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a>Włącz metodę płatności na koncie klienta na stronie kasy w witrynie handlu elektronicznego B2B

Aby włączyć metodę płatności na koncie klienta na stronie kasy w witrynie handlu elektronicznego B2B, wykonaj następujące kroki.

1. W narzędziu do tworzenia witryn Commerce znajdź i edytuj stronę kasy lub fragment, który zawiera moduł kasy dla witryny handlu elektronicznego B2B.
1. W gnieździe **Kontener sekcji wyewidencjonowywania** wybierz opcję **Dodaj moduł**, a następnie dodaj moduł **Płatność na konto klienta**.
1. Umieść moduł **Płatność na konto klienta**, zaznaczając wielokropek (**...**), a następnie w razie potrzeby **Przenieś w górę** lub **Przenieś w dół**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a>Potwierdź, że metoda płatności na koncie odbiorcy została włączona i opublikowana

Aby potwierdzić, że metoda płatności na koncie klienta została włączona, wykonaj następujące kroki.

1. Zaloguj się w witrynie handlu elektronicznego.
1. Dodaj produkt do koszyka.
1. Przechodzenie do strony realizacji transakcji. Powinna zostać wyświetlony nowa metoda płatności na **Koncie odbiorcy**.

## <a name="work-with-credit-limits"></a>Pracuj z limitami kredytu

Gdy w witrynie B2B są włączone możliwości płatności na kontach klientów, organizacje zwykle chcą pokazywać informacje dotyczące limitów kredytowych i sald limitów kredytowych podczas procesu przechwytywania zamówienia. Limit kredytu dla odbiorcy jest definiowany za pomocą właściwości **Limit kredytu** na skróconej karcie **Kredyty i windykacja** rekordu odbiorcy w centrali commerce. Jednak w scenariuszach B2B zamówienie wystawiane przez klienta powinno być często fakturowane na konto organizacji, do której należy odbiorca. Dlatego należy ustawić właściwość **konta faktury** na skróconej karcie **Faktura i dostawa** rekordu odbiorcy jako identyfikator konta odbiorcy organizacji. Następnie, gdy odbiorca złoży zamówienie w witrynie B2B, zamówienie zostanie zafakturowane dla organizacji. W lokacji B2B będzie także zamiast limitu kredytowego zdefiniowanego w rekordzie odbiorcy limit kredytowy organizacji.

Obliczanie limitu kredytu i saldo pokazywane w witrynie sieci web B2B zależy od ustawienia właściwości **Typ limitu kredytu** w centrali Commerce. Lokalizacja tej właściwości zmienia się w zależności od tego, czy funkcja **Zarządzanie kredytem** jest włączona w obszarze roboczym **Zarządzanie funkcjami**:

- Jeśli funkcja **Zarządzanie kredytem** jest włączona, właściwość znajduje się na skróconej karcie **Limity kredytu** i windykacji w parametrach **Kredyty i windykacja \> Ustawienia \> Parametry kredytu i windykacji \> Kredyt**. 
- Jeśli funkcja **Zarządzanie kredytem** jest wyłączona, właściwość znajduje się w obszarze **Ocena kredytu** w **Należności \> Konfiguracja \> Parametry należności \> Ocena zdolności kredytowej**.

Wartości, które obsługuje właściwość **Typu Limit kredytu**, to **Brak**, **Saldo**, **Saldo + dokument dostawy lub dokument przyjęcia produktów** oraz **Saldo + Wszystko**. Aby uzyskać więcej informacji o tych wartościach, zobacz [typy limitu kredytu](/dynamics365/supply-chain/sales-marketing/credit-limits-customers).

> [!NOTE]
> Zaleca się, aby we właściwości **Typ limitu kredytu** ustawić wartość **Saldo + dokument dostawy lub dokument produktu**, aby otwarte zamówienia sprzedaży nie wpływały na obliczanie salda. Następnie, jeśli odbiorcy będą składać przyszłe zamówienia, nie muszą oznaczać, że będą mieć wpływ na ich bieżące saldo.

Inną właściwością mającą wpływ na zamawianie a konta jest właściwość **Wymagany limit kredytu**, która znajduje się na skróconej karcie **Kredyty i windykacja** w rekordzie odbiorcy. Ustawienie tej właściwości na wartość **Tak** dla określonych odbiorców może wymusić w systemie sprawdzanie limitu kredytu, nawet jeśli właściwość typu **Limit kredytu** została ustawiona na **Brak**, aby określić, że limit kredytu nie powinien być sprawdzany dla żadnego odbiorcy.

Obecnie klient korzystający z formy płatności akonto nie może zapłacić więcej niż pozostała kwota kredytu za zamówienie. Na przykład, jeśli pozostałe saldo kredytu klienta wynosi 1000 USD, ale zamówienie ma wartość 1200 USD, klient może zapłacić tylko 1000 USD za pomocą metody na koncie. Klient musi wtedy użyć innej metody płatności, by zapłacić saldo. W przyszłym wydaniu, w konfiguracji Commerce, użytkownicy będą mogli wydawać więcej niż wynosi ich limit kredytowy podczas składania zamówień.

Moduł **Kredyty i windykacja** ma nowe możliwości zarządzania kredytem. Aby włączyć te możliwości, włącz funkcję **Zarządzanie kredytem** w obszarze roboczym **Zarządzanie funkcjami**. Jeden z nowych możliwości umożliwia wstrzymywanie zamówień sprzedaży na podstawie reguł blokowania. Osoba kierownika ds. kredytów może następnie zwolnić lub odrzucić zamówienia po dalszej analizie. Możliwość wstrzymywania zamówień sprzedaży nie ma jednak zastosowania do zamówień commerce, ponieważ zamówienia sprzedaży często mają przedpłatę, a funkcja **Zarządzanie kredytem** nie obsługuje w pełni scenariuszy przedpłat. 

Niezależnie od tego, czy funkcja **Zarządzanie kredytami** jest włączona, jeśli saldo klienta przekroczy limit kredytowy podczas realizacji zamówienia, zamówienia sprzedaży nie zostaną wstrzymane. W zamian usługa Commerce będzie generować komunikat ostrzegawczy lub komunikat o błędzie, w zależności od wartości pola **Komunikat przy przekroczeniu limitu kredytu** na skróconej karcie Limity **kredytowe**.

Właściwość **Wyklucz z zarządzania kredytami** zapobiegająca zawieszaniu zamówień sprzedaży w ramach usługi handlowej znajduje się w nagłówku zamówienia sprzedaży (**Handel detaliczny \> klientów \> Wszystkie zamówienia sprzedaży**). Jeśli właściwość ma wartość **Tak** (wartość domyślna) dla zamówień sprzedaży w handlu, zamówienia zostaną wykluczone z wstrzymanego przepływu pracy zarządzania kredytem. Chociaż właściwość nosi nazwę **Wyklucz z zarządzania kredytem**, zdefiniowany limit kredytu będzie nadal używany podczas realizacji zamówienia. Zamówienia właśnie nie będą wstrzymane.

Możliwość wstrzymywania zamówień sprzedaży w usługach Commerce na podstawie reguł blokowania jest planowana dla przyszłych wersji handlowych. Dopóki nie będzie obsługiwane, jeśli musisz wymusić przechodzenie zamówień sprzedaży w ramach usługi Commerce przez nowe przepływy zarządzania kredytami, możesz dostosować następujące pliki XML w rozwiązaniu Visual Studio. W plikach zmodyfikuj logikę, tak aby flaga **CredManExcludeSalesOrder** mieć wartość **No**. W ten sposób właściwość **Wyklucz z zarządzania kredytami** zostanie domyślnie ustawiona na **Nie** dla zamówień sprzedaży w usłudze Commerce.

- RetailCreateCustomerOrderExtensions_CredMan_Extension.xml
- RetailCallCenterOrderExtensions_CredMan_Extension.xml

Jeśli flaga **CredManExcludeSalesOrder** ma wartość **No**, a odbiorca b2B może kupować w sklepach za pomocą aplikacji punkt sprzedaży (POS), księgowanie transakcji kasowych i transakcji przenoszenia może się nie powieść. Na przykład istnieje reguła blokowania płatności gotówkowej, a odbiorca B2B zakupił pewne towary w sklepie za pomocą gotówki. W tym przypadku wynikowe zamówienie sprzedaży nie zostanie pomyślnie zafakturowane, ponieważ zostanie wstrzymane. W związku z tym księgowanie nie powiedzie się. Z tego powodu po zaimplementowaniu tego dostosowania zaleca się testowanie na zakończenie.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie witryny wykorzystywanej na potrzeby handlu elektronicznego B2B](set-up-b2b-site.md)

[Zarządzanie partnerami biznesowymi B2B przy użyciu hierarchii klientów](partners-customer-hierarchies.md)

[Zarządzanie użytkownikami partnerów biznesowych w witrynach handlu elektronicznego B2B](manage-b2b-users.md)

[Ustawianie limitów ilości produktów dla witryn B2B handlu elektronicznego](quantity-limits.md)

[Aktualizacje zestawu SDK i biblioteki modułów](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
