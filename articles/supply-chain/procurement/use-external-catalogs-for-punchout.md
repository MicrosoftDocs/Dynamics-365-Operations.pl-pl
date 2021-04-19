---
title: Używanie katalogów zewnętrznych dla rozwiązania PunchOut e-procurement
description: W tym temacie wyjaśniono sposób używania zewnętrznych katalogów do tworzenia i przesyłania zapotrzebowań.
author: kamaybac
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchVendorPortalRequests, CatExternalCatalogBasketWizard, CatExternalCatalogPunchoutDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a839f672454105871a101c190ee87d701e58db4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811069"
---
# <a name="use-external-catalogs-for-punchout-e-procurement"></a>Używanie katalogów zewnętrznych dla rozwiązania PunchOut e-procurement

[!include [banner](../includes/banner.md)]

Używając zewnętrznych katalogów w elektronicznym systemie zaopatrzenia z dynamicznie dostępnym katalogiem dostawcy, nie trzeba przechowywać informacji o produktach dostawców we własnych danych użytkownika. Zamiast tego koszyk w witrynie internetowej dostawcy jest konwertowany na wiersze zapotrzebowania zawierające poprawne informacje o produktach. 

Należy unikać utrzymywania opisów i cen produktów dostawców wśród własnych danych głównych produktów. Zamiast tego należy używać zewnętrznych katalogów w scenariuszu elektronicznego systemu zaopatrzenia z dynamicznie dostępnym katalogiem dostawcy. Wtedy gdy pracownicy tworzą zapotrzebowania, mogą dynamicznie sięgnąć do witryny katalogu zewnętrznego dostawcy (innymi słowy opuszczają własny system i przechodzą do witryny dostawcy). Produkty dodane do koszyka w witrynie internetowej dostawcy mogą być następnie konwertowane na wiersze zapotrzebowania. W związku z tym otrzymujesz poprawne informacje o produktach: identyfikator produktu, nazwę, cenę itd.

Aby korzystać z zewnętrznych katalogów, pracownik musi utworzyć zapotrzebowania na stronie **Moje zapotrzebowania na zakup**.

Pracownik, który utworzył zapotrzebowanie, jest nazywany wystawcą zapotrzebowania. Wystawca może wykonywać następujące zadania:

Używanie akcji wiersza **Katalogi zewnętrzne** w celu otwarcia strony zawierającej wszystkie katalogi zewnętrzne dostępne dla określonego zleceniodawcy, kupującej firmy i przyjmującej jednostki operacyjnej.

W zależności od posiadanych uprawnień zmiana zleceniodawcy, kupującej firmy i przyjmującej jednostki operacyjnej. Zmiana tych wartości może powodować zmianę listy zewnętrznych katalogów dostępnych dla zleceniodawcy. Dostępne zewnętrzne katalogi zależą od obecnie aktywnych zasad zakupów w kupującej firmie lub przyjmującej jednostce operacyjnej. Zasady te mogą przyznawać lub blokować dostęp do określonych kategorii zaopatrzenia. Może to wpływać na listę zewnętrznych katalogów mapowanych na te kategorie zaopatrzenia.

Aby uzyskać więcej informacji o zasadach, zobacz [Omówienie zasad zakupów](../procurement/purchase-policies.md).

- Aby znaleźć zewnętrzne katalogi dla określonych kategorii zaopatrzenia, wpisz tekst w polu wyszukiwania katalogów.
- Aby dodać produkty z zewnętrznego katalogu dostawcy w witrynie internetowej dostawcy, kliknij zewnętrzny katalog. Następnie dodaj produkty do koszyka i zakończ transakcję. Wiersze koszyka zostaną przeniesione do rozwiązania Microsoft Dynamics 365.

Jeśli istnieje wiele kategorii zaopatrzenia, wybierz odpowiednią kategorię zaopatrzenia przed dodaniem wierszy do zapotrzebowania.
Gdy wiersze zostaną dodane do zapotrzebowania, można dodać więcej wierszy bez korzystania z zewnętrznych katalogów. Alternatywnie możesz dodawać wiersze nadal z zewnętrznych katalogów.

Gdy zapotrzebowanie jest gotowe, użyj akcji **Przepływ pracy** > **Prześlij**, aby je wysłać do zatwierdzenia.

### <a name="additional-resources"></a>Dodatkowe zasoby

- [Konfigurowanie katalogu zewnętrznego dla rozwiązania PunchOut e-procurement](set-up-external-catalog-for-punchout.md)
- [Udoskonalenia cXML dotyczące zakupów](purchasing-cxml-enhancements.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]