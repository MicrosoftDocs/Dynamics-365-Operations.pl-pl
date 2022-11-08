---
title: Dynamics 365 Payment Connector dla Adyen — omówienie
description: Ten artykuł zawiera omówienie modułu Microsoft Dynamics 365 Payment Connector dla Adyen.
author: rassadi
ms.date: 10/27/2022
ms.topic: overview
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 931fc69cda8daa2e06b6f1155fbf0369fd2bca55
ms.sourcegitcommit: 435e69160dbd7f9c61b37ac4440285a5df144622
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2022
ms.locfileid: "9728310"
---
# <a name="dynamics-365-payment-connector-for-adyen-overview"></a>Dynamics 365 Payment Connector dla Adyen — omówienie

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie łącznika Microsoft Dynamics 365 Payment Connector dla Adyen oraz pełną listę obsługiwanych funkcji i możliwości. Pokrewne artykuły obejmują konto użytkownika Adyen, konfigurację łącznika, często zadawane pytania oraz wskazówki dotyczące rozwiązywania pewnych typowych problemów.

## <a name="key-terms"></a>Kluczowe terminy

| Okres | Opis |
|---|---|
| Łącznik płatności | Rozszerzenie ułatwiające komunikację między Microsoft Dynamics 365 Commerce (i skojarzonymi składnikami) a usługą płatności. Łącznik jest opisany w tym artykule był zaimplementowany przy użyciu standardowego zestawu SDK płatności. |
| Z kartą | Odnosi się do transakcji płatności, w przypadku których karta fizyczna jest prezentowana i wkładana do łącznika terminalu punktu sprzedaży Dynamics 365. |
| Bez karty | Odnosi się do transakcji płatności, w których nie ma karty fizycznej, takich jak scenariusze handlu elektronicznego lub biura obsługi klienta. W przypadku tych scenariuszy informacje związane z płatnością są wprowadzane ręcznie w witrynie handlu elektronicznego, w przepływie biura obsługi lub w terminalu punktu sprzedaży albo płatności. |

## <a name="supported-features-functionality-versions-and-terminals"></a>Obsługiwane funkcje, możliwości, wersje i terminale

W gotowym programie Dynamics 365 Payment Connector dla Adyen jest używany standardowy zestaw SDK płatności. W związku z tym nie ma specjalnych możliwości, które nie są także dostępne dla innych łączników płatności.

### <a name="supported-versions"></a>Obsługiwane wersje

#### <a name="microsoft-dynamics-365-supported-versions"></a>Obsługiwane wersje Microsoft Dynamics 365
Bezpośredni, gotowy łącznik Dynamics 365 Payment Connector dla Adyen jest obsługiwany w Microsoft Dynamics 365 Finance w wersji 8.1.3 (styczeń 2019) i późniejszej oraz w Microsoft Dynamics 365 Retail w wersji 8.1.3 i późniejszej. Niemniej jednak inne firmy nadal mogą tworzyć łączniki płatności dla Adyen w starszych wersjach systemu Microsoft Dynamics 365.

#### <a name="supported-adyen-firmware-versions"></a>Obsługiwane wersje oprogramowania układowego Adyen

Poniżej opisano minimalne i maksymalne wersje oprogramowania ukłądowego Adyen, które są obsługiwane w przypadku każdej wersji Microsoft Dynamics 365 Retail POS.

---

# <a name="10025"></a>[10.0.25](#tab/10-0-25)
### <a name="dynamics-365-retail-pos-version-10025"></a>Wersja 10.0.25 Dynamics 365 Retail POS
| Minimalna wersja oprogramowania układowego Adyen | Maksymalna wersja oprogramowania układowego Adyen |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_73p6 |

# <a name="10026"></a>[10.0.26](#tab/10-0-26)
### <a name="dynamics-365-retail-pos-version-10026"></a>Wersja 10.0.26 Dynamics 365 Retail POS
| Minimalna wersja oprogramowania układowego Adyen | Maksymalna wersja oprogramowania układowego Adyen |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p13 |

# <a name="10027"></a>[10.0.27](#tab/10-0-27)
### <a name="dynamics-365-retail-pos-version-10027"></a>Wersja 10.0.27 Dynamics 365 Retail POS
| Minimalna wersja oprogramowania układowego Adyen | Maksymalna wersja oprogramowania układowego Adyen |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p13 |

# <a name="10028"></a>[10.0.28](#tab/10-0-28)
### <a name="dynamics-365-retail-pos-version-10028"></a>Wersja 10.0.28 Dynamics 365 Retail POS
| Minimalna wersja oprogramowania układowego Adyen | Maksymalna wersja oprogramowania układowego Adyen |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p22 |

# <a name="10029"></a>[10.0.29](#tab/10-0-29)
### <a name="dynamics-365-retail-pos-version-10029"></a>Wersja 10.0.29 Dynamics 365 Retail POS
| Minimalna wersja oprogramowania układowego Adyen | Maksymalna wersja oprogramowania układowego Adyen |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_78p6 |

# <a name="10030"></a>[10.0.30](#tab/10-0-30)
### <a name="dynamics-365-retail-pos-version-10030"></a>Wersja 10.0.30 Dynamics 365 Retail POS
| Minimalna wersja oprogramowania układowego Adyen | Maksymalna wersja oprogramowania układowego Adyen |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_78p6 |

---

> [!NOTE]
> Po przetestowaniu większe wersji Adyen może wydać mniejszą aktualizację wersji. Dopóki jest obsługiwana wersja główna, w tej samej wersji pomocniczej muszą być dostępne tylko aktualizacje wersji pomocniczej. Te aktualizacje są zwykle bardzo docelowymi poprawkami i nie znajdują się na drodze pełnego ponownego testowania, dopóki ta sama wersja główna została przetestowana. Aktualizacje nie powinny przekraczać maksymalnej wartości wersji oprogramowania układowego Adyen wymienionej w dokumentacji. 
>
> Migrowanie z wersji oprogramowania układowego Adyen w wersji wcześniejszej niż wersja 53 do wersji 53 wymaga bazy wiedzy programu punktu sprzedaży **4577957** dla miesięcznych aktualizacji programu Commerce w wersjach od 10.0.11 do 10.0.14. Jeśli jedna z tych wersji jest w użyciu i nie zawiera poprawki, funkcja końcowego uaktualnienia terminalu płatności będzie zezwalać tylko na płatności za pośrednictwem usługi NFC. Zastosowanie poprawki do punktu sprzedaży rozwiąże ten problem. Jeśli wersja punktu sprzedaży jest starsza niż wersja 10.0.11, należy złożyć wniosek o pomoc techniczną z uwagą, że dla baza wiedzy **4577957** jest wymagana dla nieaktualnego MPOS.
> 
> W przypadku wersji oprogramowania układowego Adyen od 59p7 do 62p9 operacja **wypłaty gotówki na karcie upominkowej** żąda wpisu PIN dwukrotnie w scenariuszach, w których karta jest wprowadzana ręcznie. Ten problem nie jest odtwarzany po przeciągnięciu karty upominkowej. Adyen jest w trakcie badań. 

### <a name="supported-payment-terminals"></a>Obsługiwane terminale płatnicze
Łącznik Dynamics 365 Payment Connector dla Adyen wykorzystuje niezależny od urządzenia [interfejs API terminala płatności Adyen](https://www.adyen.com/blog/introducing-the-terminal-api). Obsługuje wszystkie terminale płatności, które obsługuje ten interfejs programowania aplikacji (API). Aby uzyskać pełną listę obsługiwanych terminali do płatności, odwiedź stronę [terminale Adyen w punkcie sprzedaży](https://www.adyen.com/pos-payments/terminals).

### <a name="supported-payment-instruments"></a>Obsługiwane instrumenty płatnicze

#### <a name="supported-debit-and-credit-cards"></a>Obsługiwane karty debetowe i kredytowe

| Marka | Wariant | Z kartą | Handel elektroniczny | Biuro obsługi |
|---|---|:-:|:-:|:-:|
| MasterCard | Środki | ✔ | ✔ | ✔ |
| MasterCard | Uznanie | ✔ | ✔ | ✔ |
| MasterCard | Alpha Bank Bonus | ✔ | ✔ | ✔ |
| MasterCard | Apple Pay | ✔ |  |  |
| MasterCard | Samsung Pay | ✔ |  |  |
| MasterCard | Maestro | ✔ | ✔ | ✔ |
| MasterCard | Maestro Samsung Pay | ✔ |  |  |
| MasterCard | Maestro UK | ✔ | ✔ | ✔ |
| VISA | Środki | ✔ | ✔ | ✔ |
| VISA | Uznanie | ✔ | ✔ | ✔ |
| VISA | Alpha Bank Bonus | ✔ | ✔ | ✔ |
| VISA | Android Pay | ✔ |  |  |
| VISA | Apple Pay | ✔ |  |  |
| VISA | Samsung Pay | ✔ |  |  |
| VISA | VISA Checkout | ✔ | ✔ | ✔ |
| VISA | VISA Dankort | ✔ | ✔ | ✔ |
| VISA | VISA Hipotecario | ✔ | ✔ | ✔ |
| VISA | Karta VISA Aravia | ✔ | ✔ | ✔ |
| AMEX | Środki | ✔ | ✔ | ✔ |
| AMEX | Uznanie | ✔ | ✔ | ✔ |
| AMEX | Android Pay | ✔ |  |  |
| AMEX | Apple Pay | ✔ |  |  |
| AMEX | Samsung Pay | ✔ |  |  |
| AMEX | AMEX Commercial | ✔ | ✔ | ✔ |
| AMEX | AMEX Consumer | ✔ | ✔ | ✔ |
| AMEX | AMEX Corporate | ✔ | ✔ | ✔ |
| AMEX | AMEX Small Business | ✔ | ✔ | ✔ |
| Discover | Standardowo | ✔ | ✔ | ✔ |
| Discover | Android Pay | ✔ |  |  |
| Discover | Apple Pay | ✔ |  |  |
| Discover | Samsung Pay | ✔ |  |  |
| Diners   | Standardowo | ✔ | ✔ | ✔ |
| Dineromail | Standardowo | ✔ | ✔ | ✔ |
| JCB | Standardowo | ✔ | ✔ | ✔ |
| Union Pay\* | Standardowo | ✔ |  |  |
| Interac Debit\* | Standardowo | ✔ |  |  |

\*Tokeny karty cyklicznej Interac i Union Pay nie są dostarczone przez Adyen, więc nie mogą być obsługiwane w przypadku transakcji, w których nie ma kart.

#### <a name="supported-gift-cards"></a>Obsługiwane karty upominkowe
| Schemat | Z kartą | Bez karty |
|---|:-:|---|
| Givex | ✔ | ✔ |
| SVS | ✔ | ✔ |

Aby obsługiwać te zewnętrzne schematy kart upominkowych za pośrednictwem łącznika płatności usługi Dynamics 365 Payment Connector dla Adyen, należy wykonać dodatkowe kroki. Aby uzyskać więcej informacji, zobacz [Pomoc techniczna dla zewnętrznych kart upominkowych](/dynamics365/unified-operations/retail/dev-itpro/gift-card).

#### <a name="supported-wallets"></a>Obsługiwane portfele

| Schemat | Z kartą | Bez karty |
|---|---|---|
| Alipay | Obsługa zostanie dodana w przyszłej wersji. | Nr |
| WeChat | Obsługa zostanie dodana w przyszłej wersji. | Nr |

#### <a name="supported-card-present-input-methods"></a>Obsługiwane metody wprowadzania danych na karcie
| Metoda wprowadzania | Obsługiwana | Notatki |
|---|:-:|---|
| Wsunięcie | ✔ | |
| Przeciąganie | ✔ | |
| Dotknięcie | ✔ | |
| Ręczne wprowadzanie za pomocą interfejsu użytkownika punktu sprzedaży. |  | Obecnie nieobsługiwane |
| Ręczne wprowadzanie za pomocą terminalu płatności. | ✔ | Obsługuje ręczne wprowadzanie kart kredytowych, debetowych i upominkowych wraz ze wprowadzeniem numeru PIN. | 


#### <a name="supported-card-present-countries"></a>Obecnie obsługiwane karty z krajów

W następujących krajach są dostępne składniki Commerce, a karta obsługuje program Adyen. Aby uzyskać aktualną dostępność rozwiązania Commerce, odwiedź [stronę Dostępności międzynarodowej](/dynamics365/get-started/availability).

| Kraj | Obsługiwana |
| --- | :-: |
| Australia | ✔ |
| Austria | ✔ |
| Belgia | ✔ |
| Kanada | ✔ |
| Republika Czeska | ✔ |
| Dania | ✔ |
| Estonia | ✔ |
| Finlandia | ✔ |
| Francja | ✔ |
| Niemcy | ✔ |
| SRA Hongkong | ✔ |
| Węgry | ✔ |
| Islandia | ✔ |
| Irlandia | ✔ |
| Włochy | ✔ |
| Japonia | Przyszłe wydanie |
| Łotwa | ✔ |
| Litwa | ✔ |
| Malezja | ✔ |
| Holandia | ✔ |
| Nowa Zelandia | ✔ |
| Norwegia | ✔ |
| Polska | ✔ |
| Singapur | ✔ |
| Szwajcaria | ✔ |
| Hiszpania | ✔ |
| Szwecja | ✔ |
| Szwajcaria | ✔ |
| Zjednoczone Królestwo | ✔ |
| Stany Zjednoczone | ✔ |
| Brazylia | Przyszłe wydanie |

#### <a name="supported-card-not-present-countries"></a>Obecnie nieobsługiwane karty z krajów

W przypadku transakcji kartami nie są obsługiwane następujące kraje. [Skontaktuj się z Adyen](https://www.adyen.com/contact/sales), aby uzyskać szczegółowe informacje dotyczące pomocy technicznej dotyczącej określonego kraju. Aby uzyskać aktualną dostępność rozwiązania Commerce, odwiedź [stronę Dostępności międzynarodowej](/dynamics365/get-started/availability).

| Kraj | 
| --- |
| Argentyna |
| Armenia |
| Australia |
| Austria |
| Bahrajn |
| Belgia |
| Brazylia |
| Bułgaria |
| Kanada |
| Chile |
| Chiny |
| Kolumbia |
| Chorwacja |
| Cypr |
| Republika Czeska  |
| Dania |
| Egipt |
| Estonia |
| Finlandia |
| Francja |
| Gruzja |
| Niemcy |
| Gibraltar |
| Grecja |
| Guernsey |
| SRA Hongkong |
| Węgry |
| Islandia |
| Indie |
| Indonezja |
| Irlandia |
| Wyspa Man |
| Izrael |
| Włochy |
| Japonia |
| Jersey |
| Korea |
| Kuwejt |
| Łotwa |
| Litwa |
| Luksemburg |
| Malezja |
| Malta |
| Meksyk |
| Maroko |
| Holandia |
| Nowa Zelandia |
| Norwegia |
| Peru |
| Polska |
| Portugalia |
| Katar |
| Rumunia |
| Arabia Saudyjska |
| Serbia |
| Singapur |
| Słowacja |
| Słowenia |
| Republika Południowej Afryki |
| Hiszpania |
| Szwecja |
| Szwajcaria |
| Tajwan |
| Tanzania |
| Tajlandia |
| Turcja |
| Zjednoczone Emiraty Arabskie (ZEA) |
| Zjednoczone Królestwo |
| Stany Zjednoczone Ameryki z Portoryko  |

#### <a name="supported-dynamics-365-payment-features"></a>Obsługiwane funkcje płatności usługi Dynamics 365

W poniższej tabeli przedstawiono zestaw funkcji, które obsługuje program Dynamics 365 Payment Connector dla Adyen. Te funkcje używają ulepszeń wprowadzonych w zestawie SDK płatności oraz niektórych składników w grudniu 2018 roku. Nie są one wyłączne dla łącznika Dynamics 365 Payment Connector dla Adyen. Aby uzyskać więcej informacji na temat sposobu pobierania ulepszeń dla różnych łączników płatności, zobacz temat [Tworzenie kompleksowej integracji płatności dla terminala płatniczego](/dynamics365/unified-operations/retail/dev-itpro/end-to-end-payment-extension).

| Schemat | Z kartą | Bez karty |
|---|:-:|:-:|
| [Saldo spieniężenia karty upominkowej](/dynamics365/unified-operations/retail/dev-itpro/gift-card-cash-out) | ✔ | |
| [Zapobieganie zduplikowanym płatnościom](/dynamics365/unified-operations/retail/duplicate-payment-protection) | ✔ | |
| Tokenizacja wielokanałowa | ✔ | ✔ |
| Połączone zwroty | ✔<br>(Począwszy od 10.0.1) | ✔<br>(Począwszy od 10.0.1) |
| [Zapisywanie płatności online](../dev-itpro/adyen-connector-listPI.md) | | ✔<br>(Począwszy od 10.0.2) | 
| [Zewnętrzne karty upominkowe do biur obsługi i handlu elektronicznego](./gift-card.md) | ✔<br>(Począwszy od 10.0.10) | 
| [Przekierowanie płatności SCA](../adyen_redirect.md) | | ✔<br>(Począwszy od 10.0.12) |
| [Dedykowane terminale płatności oraz monity o drukarkę i szuflady kasowe](../pos-multi-hws.md) | ✔<br>(Począwszy od 10.0.12) | |
| [Pomoc techniczna na poziomie zestawu SDK za pomocą łącznika Adyen](tipping.md) | ✔<br>(Począwszy od 10.0.14) | |
| [Przechwytywanie przyrostowe dla fakturowania zamówienia](incremental-capture.md) |  | ✔<br>(Począwszy od 10.0.18) |
| [Płatności portfelem](../wallets.md) |  | ✔<br>(Począwszy od 10.0.20) |
| [Google Pay z Adyen](google-pay-adyen.md) |  | ✔<br>(Począwszy od 10.0.27) |

## <a name="next-steps"></a>Następne kroki

Aby uzyskać więcej informacji na temat rejestracji i konfigurowania Dynamics 365 Payment Connector dla Adyen, zobacz temat [Konfiguracja łącznika Dynamics 365 Payment Connector dla Adyen](adyen-connector-setup.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie rozwiązania Dynamics 365 Payment Connector dla Adyen](adyen-connector-setup.md)

[Dynamics 365 Payment Connector dla Adyen — często zadawane pytania](adyen-connector-faq.md)

[Rozwiązywanie problemów z rozwiązaniem Dynamics 365 Payment Connector dla Adyen](adyen-connector-troubleshoot.md)

[Płatności — często zadawane pytania](/dynamics365/unified-operations/retail/dev-itpro/payments-retail)

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
