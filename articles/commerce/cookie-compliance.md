---
title: Zgodność z plikami cookie
description: W tym temacie opisano zagadnienia dotyczące zgodności z plikami cookie i domyślnych zasad, które są zawarte w aplikacji Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4f54b9b8130a167dbecdb13fccd7039f827f6ed0
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761328"
---
# <a name="cookie-compliance"></a>Zgodność z plikami cookie

[!include [banner](includes/banner.md)]

W tym temacie opisano zagadnienia dotyczące zgodności z plikami cookie i domyślnych zasad, które są zawarte w aplikacji Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

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

## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a>Zgoda na korzystanie z pliku cookie użytkownika witryny Commerce 

Jeśli funkcja lub moduł witryny handlu elektronicznego używa nieistotnego pliku cookie, należy uzyskać zgodę użytkownika witryny przed jego wykorzystaniem. Aby umożliwić użytkownikom witryny udostępnienie zgody na wykorzystanie pliku cookie w platformie handlu elektronicznego, autor witryny musi dodać i skonfigurować moduł udzielania zgody na pliki cookie w module nagłówka strony, aby umożliwić wysyłanie i odbieranie zgody na wykorzystanie pliku cookie. Przed wykorzystaniem na stronie nieistotnego pliku cookie musi być uzyskana zgoda użytkownika witryny.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Funkcje i możliwości dostępności](accessibility.md)

[Omówienie zgodności](compliance-overview.md)

[Dodawanie strony zasad ochrony prywatności](add-privacy-page.md)

[Zamień identyfikatory użytkowników skojarzone ze śledzonymi zmianami zawartości](replace-IDs-tracked-changes.md)

[Moduł zgody na pliki cookie](cookie-consent-module.md) 
 
[Moduł nagłówka](author-header-module.md)
