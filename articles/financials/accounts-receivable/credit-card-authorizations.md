---
title: Konfiguracja i autoryzacja karty kredytowej
description: "Ten artykuł zawiera omówienie funkcji autoryzacji kart kredytowych w programie Microsoft Dynamics 365 for Finance and Operations. Znajdują się tu informacje o konfigurowaniu usługi płatności, dodawaniu karty kredytowej do zamówienia sprzedaży oraz o unieważnianiu autoryzacji."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CreditCardProcessors, CustTable, SalesTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, Retail
ms.custom: 3041
ms.assetid: 678f6899-bfa5-439b-aaca-b4affcc338ba
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 4a6354563fdebff901498f1cd6caed3aedae668b
ms.contentlocale: pl-pl
ms.lasthandoff: 03/26/2018

---

# <a name="credit-card-setup-authorization-and-capture"></a>Konfiguracja i autoryzacja karty kredytowej

[!INCLUDE [banner](../includes/banner.md)]

[!INCLUDE [retail name](../includes/retail-name.md)]

Ten artykuł zawiera omówienie funkcji autoryzacji kart kredytowych w programie Microsoft Dynamics 365 for Finance and Operations. Znajdują się tu informacje o konfigurowaniu usługi płatności, dodawaniu karty kredytowej do zamówienia sprzedaży oraz o unieważnianiu autoryzacji.

<a name="setting-up-the-credit-card-payment-service"></a>Konfigurowanie usługi płatności kartą kredytową
------------------------------------------

Aby skonfigurować karty kredytowe, należy ustawić i aktywować usługę płatności na stronie Usługi płatności. Usługa płatności pełni rolę pomostu między firmą i bankiem, który przetwarza opłaty kartą kredytową odbiorcy. Należy skontaktować się z wystawcą karty kredytowej wymienionym w polu Łącznik płatności i skonfigurować konto u tego wystawcy. Następnie trzeba ustawić inne opcje na stronie Usługi płatności, ustawić typy kart kredytowych American Express, Discover, MasterCard na stronie Typy kart kredytowych i aktywować wystawcę jako domyślnego. Trzeba też wykonać następujące kroki, by ukończyć konfigurację:
-   Na stronie Parametry rozrachunków z odbiorcami należy określić parametry korzystania z autoryzacji karty kredytowej.
-   Na stronie Warunki płatności należy ustawić wartości płatności dla kart kredytowych. W polu Typ płatności należy wybrać opcję Karta kredytowa.
-   Na stronie Karty kredytowe klienta należy wpisać dane karty kredytowej dla klientów.

## <a name="adding-a-new-credit-card"></a>Dodawanie nowej karty kredytowej
Można tworzyć nowe rekordy kart kredytowych na stronie Odbiorcy, używając opcji Odbiorca, Ustawienia, Karta kredytowa. Można też tworzyć rekordy kart kredytowych podczas wprowadzania zamówień sprzedaży na stronie Zamówienie sprzedaży, używają opcji Zarządzaj, Odbiorca, Karta kredytowa, Rejestr.
Dodawanie karty kredytowej dla zamówienia sprzedaży
-------------------------------------

Można dodać kartę kredytową do zamówienia sprzedaży , wybierając kartę kredytową w sekcji wyszukiwania kart kredytowych na skróconej karcie Cena i rabaty na stronie Zamówienie sprzedaży. Aby rozpocząć proces autoryzacji w okienku akcji na karcie Zarządzanie wybierz opcję Karta kredytowa i Autoryzuj.
Autoryzacja karty kredytowej
-------------------------

Autoryzacja karty kredytowej polega na zweryfikowaniu numeru karty i tożsamości jej posiadacza oraz potwierdzeniu dostępnego salda kredytu. Opcjonalnie weryfikowane są wartość weryfikacji karty i adres posiadacza karty. Dostępne saldo kredytu odbiorcy jest następnie zmniejszane o kwotę faktury. Usługa płatności wysyła informację, czy karta kredytowa została przyjęta, czy odrzucona. Podczas fakturowania zamówienia sprzedaży karta kredytowa jest obciążana (autoryzowana) kwotą faktury.

### <a name="card-verification-value"></a>Wartość weryfikacji karty

Można wymagać wartości weryfikacji karty, która jest czasem określana jako kod bezpieczeństwa na karcie. Na kartach American Express jest to kod czterocyfrowy. Na kartach Discover, MasterCard i Visa są to trzy cyfry.

### <a name="address-verification"></a>Weryfikacja adresu

Informacje weryfikacji adresu są zawsze wysyłane do dostawcy płatności. Można określić, ile informacji jest wymaganych do zaakceptowania transakcji. Należy skontaktować się z dostawcą, aby określić, czy może on akceptować te informacje. Oto opcje weryfikacji adresu:
-   **Zawsze akceptuj transakcję** — akceptuj transakcję, niezależnie od wyników weryfikacji adresu.
-   **Posiadacz konta** — porównanie imienia i nazwiska z transakcji z informacjami od wystawcy karty kredytowej.
-   **Adres na fakturze** — porównanie imienia i nazwiska i adresu rozliczeniowego z transakcji z informacjami od wystawcy karty kredytowej.
-   **Kod pocztowy do faktury** — porównanie imienia i nazwiska, adresu rozliczeniowego i kodu pocztowego z transakcji z informacjami od wystawcy karty kredytowej.

## <a name="data-support"></a>Obsługa danych
Dla każdego typu karty kredytowej, który jest obsługiwany, można określić poziom obsługi danych. Poziom określa ilość informacji dotyczących transakcji, jaka jest przesyłana do usługi płatności. Należy skontaktować się z dostawcą, aby określić, czy ma on te informacje. Poniżej przedstawiono opcje poziom obsługi danych:
-   **Poziom 1** — przesłanie danych transakcji, kwoty transakcji i opisu.
-   **Poziom 2** — przesłanie informacje poziomu 1 plus adresy wysyłki i handlowca oraz informacji podatkowych.
-   **Poziom 3** — przesłanie informacji poziomu 2 plus informacji w wierszu zamówienia.

## <a name="partial-payments"></a>Płatności częściowe
Jeśli wysyłasz części zamówienia, kwota częściowego zamówienia jest rejestrowana, a autoryzacja będącą kwotą całego zamówienia jest zamykana. Nowa autoryzacja jest następnie przesyłana na pozostałą kwotę zamówienia, która nie została jeszcze wysłana.

## <a name="voiding-an-authorization"></a>Unieważnianie autoryzacji 
Abu unieważnić autoryzację karty kredytowej, można zmienić metodę płatności na inną, która nie ma typu karty kredytowej.






