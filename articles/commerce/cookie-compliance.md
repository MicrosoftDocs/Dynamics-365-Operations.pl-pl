---
title: Zgodność z plikami cookie
description: W tym temacie opisano zagadnienia dotyczące zgodności z plikami cookie i domyślnych zasad, które są zawarte w aplikacji Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 05/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8eb610eb819dee09a30368257e36dc88f855e985
ms.sourcegitcommit: 8c5b3e872825953853ad57fc67ba6e5ae92b9afe
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/24/2021
ms.locfileid: "6088394"
---
# <a name="cookie-compliance"></a>Zgodność z plikami cookie

[!include [banner](includes/banner.md)]

W tym temacie opisano zagadnienia dotyczące zgodności z plikami cookie i domyślnych zasad, które są zawarte w aplikacji Microsoft Dynamics 365 Commerce.

Prywatność jest ważnym czynnikiem, gdy używane są technologie śledzenia, które wpływają na klientów usługi e-Commerce. Ze względu na standardy zgodności z zasadami ochrony prywatności, takimi jak Ogólne rozporządzenie o ochronie danych (RODO) w Unii Europejskiej (UE), należy wziąć pod uwagę elektroniczne wytyczne dotyczące prywatności w odniesieniu do wszystkich witryn, które są obecnie aktywne. Ponieważ wiele witryn e-Commerce jest domyślnie dostępnych globalnie, ważne jest, aby zapoznać się ze standardami zgodności dla witryny e-Commerce.

Aby dowiedzieć się więcej na temat podstawowych zasad stosowanych przez Microsoft w przypadku zgodności z plikami cookie, odwiedź [Centrum zaufania Microsoft](https://www.microsoft.com/trust-center). W tej witrynie można również znaleźć więcej informacji na temat obszarów zgodności i ochrony prywatności.

W poniższej tabeli przedstawiono bieżące listy odwołań plików cookie umieszczanych przez witryny Dynamics 365 Commerce.

| Nazwa pliku cookie                               | Użycie                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| .AspNet.Cookies                             | Przechowuj pliki cookie uwierzytelniania Azure Active Directory (Azure AD) od firmy Microsoft dla rejestracji jednokrotnej (SSO). Przechowuje zaszyfrowane informacje główne użytkownika (imię, nazwisko, adres e-mail). |
| &#95;msdyn365___cart&#95;                           | Identyfikator koszyka używany do uzyskania listy produktów dodanych do wystąpienia koszyka. |
| &#95;msdyn365___ucc&#95;                            | Śledzenie zgody na zgodność z plikami cookie.                          |
| ai_session                                  | Wykrywa, ile sesji użytkownika zostało dołączonych do niektórych stron i funkcji aplikacji. |
| ai_user                                     | Wykrywa liczbę osób korzystających z aplikacji i jej funkcji. Użytkownicy są zliczani przy użyciu identyfikatorów anonimowych. |
| b2cru                                       | Umożliwia dynamiczne przechowywanie adresów URL przekierowań.                              |
| JSESSIONID                                  | Używany przez łącznika płatności Adyen do przechowywania sesji użytkownika.       |
| OpenIdConnect.nonce.&#42;                       | Uwierzytelnianie                                               |
| x-MS-CPIM-cache:.&#42;                          | Używane do obsługi stanu żądania.                      |
| x-ms-cpim-csrf                              | Token Fałszerstwo żądania międzywitrynowego (CRSF) używany do ochrony przed CRSF.     |
| x-ms-cpim-dc                                | Używany do routowania żądań do odpowiedniego wystąpienia serwera uwierzytelniania produkcji. |
| x-ms-cpim-rc.&#42;                              | Używany do routowania żądań do odpowiedniego wystąpienia serwera uwierzytelniania produkcji. |
| x-ms-cpim-slice                             | Używany do routowania żądań do odpowiedniego wystąpienia serwera uwierzytelniania produkcji. |
| x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0 | Używane do obsługi sesji SSO.                        |
| x-ms-cpim-trans                             | Służy do śledzenia transakcji (liczba otwartych kart uwierzytelniających się w odniesieniu do oddziału firmy (B2C)), w tym bieżącej transakcji. |
| \_msdyn365___muid_                            | Używane, jeśli Eksperymentowanie jest aktywowane dla środowiska; używany jako identyfikator użytkownika do celów eksperymentalnych. |
| \_msdyn365___exp_                             | Używane, jeśli Eksperymentowanie jest aktywowane dla środowiska; używany do pomiaru równoważenia obciążenia wydajnościowego.         |
| d365mkt                                       | Używane, jeśli wykrywanie lokalizacji w celu śledzenia adresu IP użytkownika dla sugestii lokalizacji sklepu jest włączone w kreatorze stron Commerce pod adresem **Ustawienia strony > Ogólne > Włącz wykrywanie sklepu w oparciu o lokalizację**.      |

Jeśli użytkownik witryny wybierze jakiekolwiek łącza do mediów społecznościowych w witrynie, pliki cookie z poniższej tabeli będą również śledzone w jego przeglądarce.


| Domena                      | Cookie               | opis                                                  | Źródło                                          |
| --------------------------- | ------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| .linkedin.com                | UserMatchHistory         | Synchronizacja identyfikatora LinkedIn ogłoszeń                                      | LinkedIn kanału informacyjnego i znacznika szczegółówych informacji                                |
| .linkedin.com               | li_sugr                  | Identyfikator przeglądarki                                           | Znacznik szczegółowych informacji o LinkedIn, jeśli adres IP nie znajduje się w wyznaczonym kraju |
| .linkedin.com               | BizographicsOptOut       | Określa stan opcji śledzenia przez inne firmy.              | Kontrolki gości LinkedIn i branżowe strony rezygnacji           |
| .linkedin.com               | \_guid                    | Identyfikator przeglądarki dla Google Ads.                            | Kanał informacyjny LinkedIn                                                |
| .linkedin.com               | li_oatml                 | Pośredni identyfikator członka do śledzenia konwersji, ponownego kierowania i analiz. | Reklamy LinkedIn i znaczniki szczegółówych informacji                                |
| Różne domeny własne | li_fat_id                | Pośredni identyfikator członka do śledzenia konwersji, ponownego kierowania i analiz. | Reklamy LinkedIn i znaczniki szczegółówych informacji                                |
| .adsymptotic.com            | U                        | Identyfikator przeglądarki                                           | Znacznik szczegółowych informacji o LinkedIn, jeśli adres IP nie znajduje się w wyznaczonym kraju |
| .linkedin.com                | bcookie                  | Plik cookie identyfikatora przeglądarki                                            | Żądania do LinkedIn                                         |
| .linkedin.com                | bscookie                 | Zabezpieczanie pliku cookie przeglądarki                                        | Żądania do LinkedIn                                         |
| .linkedin.com               | lang                     | Umożliwia ustawienie domyślnych ustawień regionalnych i języka.                                 | Żądania do LinkedIn                                         |
| .linkedin.com                | lidc                     | Służy do wyboru trasy.                                             | Żądania do LinkedIn                                         |
| .linkedin.com               | aam_uuid                 | Plik cookie Menedżera odbiorców Adobe                                                     | Ustaw dla synchronizacji identyfikatorów                                              |
| .linkedin.com               | \_ga                      | Plik cookie Google Analytics                                            | Google Analytics                                             |
| .linkedin.com               | \_gat                     | Plik cookie Google Analytics                                             | Google Analytics                                             |
| .linkedin.com               | liap                     | Plik cookie Google Analytics                                             | Google Analytics                                             |
| .linkedin.com               | lissc                    |                                                              |                                                              |
| .facebook.com               | c_user                   | Plik cookie zawiera identyfikator użytkownika, który jest aktualnie zalogowanym użytkownikiem.  |   Facebook                                                           |
| .facebook.com               | datr                     | Służy do identyfikacji przeglądarki internetowej używanej do łączenia się z Facebook niezależnie od zalogowanego użytkownika. | Facebook                                                             |
| .facebook.com               | wd                       | Przechowuje wymiary okna przeglądarki i jest używany przez Facebook do optymalizacji renderowania strony. | Facebook                                                             |
| .facebook.com               | xs                       | Numer dwucyfrowy reprezentujący numer sesji. Druga część wartości jest wpisem tajnym sesji. |  Facebook                                                            |
| .facebook.com               | fr                       | Zawiera unikatową przeglądarkę i identyfikator użytkownika, służące do wyświetlania reklam docelowych. |  Facebook                                                            |
| .facebook.com               | sb                       | Służy do ulepszania sugestii znajomych na Facebook.                                |  Facebook                                                            |
| .facebook.com               | spin                     |                                                              |  Facebook                                                            |
| .twitter.com                | guest_id                 |                                                              |  Twitter                                                            |
| .twitter.com                | kdt                      |                                                              |  Twitter                                                             |
| .twitter.com                | personalization_id       | Plik cookie zawiera identyfikator użytkownika, który jest aktualnie zalogowanym użytkownikiem.  |  Twitter                                                             |
| .twitter.com                | remember_checked_on      |                                                              | Twitter                                                              |
| .twitter.com                | twid                     |                                                              |  Twitter                                                             |
| .pinterest.com              | \_auth                    | Plik cookie zawiera identyfikator użytkownika, który jest aktualnie zalogowanym użytkownikiem.  |   Pinterest                                                           |
| .pinterest.com              | \_b                       |                                                              |   Pinterest                                                           |
| .pinterest.com              | \_pinterest_pfob          |                                                              |  Pinterest                                                            |
| .pinterest.com              | \_pinterest_referrer      | Plik cookie zawiera strony, gdy użytkownik wybierze przycisk Pinterest.      |  Pinterest                                                            |
| .pinterest.com              | \_pinterest_sess          | Plik cookie zawiera strony, gdy użytkownik wybierze przycisk Pinterest.      |  Pinterest                                                            |
| .pinterest.com              | \_routing_id              |                                                              |  Pinterest                                                            |
| .pinterest.com              | bei                      |                                                              |  Pinterest                                                            |
| .pinterest.com              | cm_sub                   | Zawiera identyfikator użytkownika i sygnaturę czasową podczas tworzenia pliku cookie. |  Pinterest                                                            |
| .pinterest.com              | csrftoken                | Plik cookie zawiera strony, gdy użytkownik wybierze przycisk Pinterest.      | Pinterest                                                             |
| .pinterest.com              | sessionFunnelEventLogged | Plik cookie zawiera strony, gdy użytkownik wybierze przycisk Pinterest.      | Pinterest                                                             |
| .pinterest.com              | Magazyn lokalny            |                                                              |  Pinterest                                                            |
| .pinterest.com              | Pracownicy usługowi          |                                                              |  Pinterest                                                            |


## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a>Zgoda na korzystanie z pliku cookie użytkownika witryny Commerce 

Jeśli funkcja lub moduł witryny handlu elektronicznego używa nieistotnego pliku cookie, należy uzyskać zgodę użytkownika witryny przed jego wykorzystaniem. Aby umożliwić użytkownikom witryny udostępnienie zgody na wykorzystanie pliku cookie w platformie handlu elektronicznego, autor witryny musi dodać i skonfigurować moduł udzielania zgody na pliki cookie w module nagłówka strony, aby umożliwić wysyłanie i odbieranie zgody na wykorzystanie pliku cookie. Przed wykorzystaniem na stronie nieistotnego pliku cookie musi być uzyskana zgoda użytkownika witryny.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje i możliwości dostępności](accessibility.md)

[Omówienie zgodności](compliance-overview.md)

[Dodawanie strony zasad ochrony prywatności](add-privacy-page.md)

[Zamień identyfikatory użytkowników skojarzone ze śledzonymi zmianami zawartości](replace-IDs-tracked-changes.md)

[Moduł zgody na pliki cookie](cookie-consent-module.md) 
 
[Moduł nagłówka](author-header-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
