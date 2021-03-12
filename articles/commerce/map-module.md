---
title: Moduł mapy
description: W tym temacie opisano moduły mapy i sposób ich konfiguracji w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: e93358a9c76e8eb7bfb4ade4f772dece2aa5f7d3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982498"
---
# <a name="map-module"></a>Moduł mapy

[!include [banner](includes/banner.md)]


W tym temacie opisano moduły mapy i sposób ich konfiguracji w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł mapy pokazuje lokalizacje sklepów na interakcyjnej mapie, która jest renderowana przy użyciu [kontrolki sieci Web usługi Bing Maps V8](https://docs.microsoft.com/bingmaps/v8-web-control/). Klucz interfejsu API map usługi Bing jest wymagany i należy go dodać do strony udostępnione parametry Commerce headquarters. Moduły mapy zapewniają różne widoki, takie jak drogi, z powietrza i widok z ulicy, które użytkownicy mogą wybrać, aby wyświetlić lokalizacje mapy. Pozwalają również na interakcje, takie jak powiększanie i wykorzystywanie lokalizacji użytkownika.

Moduł mapy działa w połączeniu z modułem selektora sklepów, aby określić lokalizacje geograficzne sklepów, które muszą być renderowane na mapie. Moduły selektora sklepu i mapy współdziałają, gdy użytkownik wybierze sklep w jednym z tych modułów na stronie serwisu. Moduły mapy można rozszerzyć na inne scenariusze, poza interakcją z modułami selektora sklepów. Wymagane jest jednak dostosowanie modułu.

> [!NOTE]
> Moduł mapy jest dostępny w wydaniu Dynamics 365 Commerce 10.0.13.

Poniższy obraz pokazuje przykład modułu mapy, który jest używany na stronie lokalizacji sklepu.

![Przykład modułu wyboru sklepu](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a>Właściwości modułu

| Nazwa właściwości             | Wartość                 | opis |
|---------------------------|-----------------------|-------------|
| Nagłówek | Tekst | Nagłówek modułu. |
| Opcje pinezki: domyślna ikona | Wizerunek | Obraz symbolu pinezki używany w sklepach pokazywanych na mapie. |
| Opcje pinezki: aktywna ikona | Wizerunek | Obraz symbolu pinezki używany w sklepie wybranym na mapie. |
| Opcje pinezki: kolor domyślnej ikony | Ciąg znaków | Tekst lub wartość szesnastkowa koloru symboli pinezki na mapie. |
| Opcje pinezki: kolor aktywnej ikony | Ciąg znaków | Tekst lub wartość szesnastkowa koloru wybranego symboli pinezki na mapie. |
| Pokaż indeks | **Prawda** lub **Fałsz** | Jeśli dla tej właściwości ustawiono wartość **Prawda**, każdy symbol pinezki wskazujący magazyn będzie zawierał indeks. Ten indeks będzie pasował do indeksu w widoku listy wyświetlanego przez moduł wyboru sklepu. |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a>Dodaj dozwolone mapowanie adresów URL do dyrektyw zasad zabezpieczeń dotyczących zawartości oddziału

Aby moduł map mógł współdziałać z Bing Maps, musisz upewnić się, że poniższe adresy URL mapowania są dozwolone zgodnie z polityką bezpieczeństwa treści (CSP) Twojej witryny. Ta konfiguracja jest wykonywana w narzędziu do tworzenia witryn Commerce przez dodanie dozwolonych adresów URL do różnych dyrektyw CSP witryny (na przykład **img-src**). Aby uzyskać więcej informacji, zajrzyj do [zasad zabezpieczeń dotyczących zawartości](manage-csp.md). 

- Do dyrektywy **connect-src** dodaj **&#42;.bing.com**.
- Do dyrektywy **img-src**, dodaj **&#42;.virtualearth.net**.
- Do dyrektywy **script-src**, dodaj **&#42;.bing.com, &#42;.virtualearth.net**.
- Do dyrektywy **script style-src**, dodaj **&#42;.bing.com**.

## <a name="add-a-map-module-to-a-page"></a>Dodawanie modułu mapy do strony

Aby uzyskać szczegółowe informacje dotyczące konfigurowania modułu mapy na stronie, należy zapoznać się z tematem [Moduł wyboru sklepu](store-selector.md). 
 
## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł koszyka](add-cart-module.md)

[Moduł wyboru sklepu](store-selector.md)

[Zarządzanie Mapami Bing dla swojej organizacji](./dev-itpro/manage-bing-maps.md)

[Kontrolka sieci Web Bing Maps V8](https://docs.microsoft.com/bingmaps/v8-web-control/)
