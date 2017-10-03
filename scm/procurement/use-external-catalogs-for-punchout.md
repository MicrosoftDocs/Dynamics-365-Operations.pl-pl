---
title: "Używanie katalogów zewnętrznych dla rozwiązania PunchOut eProcurement"
description: "W tym temacie wyjaśniono sposób używania zewnętrznych katalogów do tworzenia i przesyłania zapotrzebowań."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 01955aefb27bd18809b35fd025c9dd1b8eb70520
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017

---

# <a name="use-external-catalogs-for-punchout-eprocurement"></a>Używanie katalogów zewnętrznych dla rozwiązania PunchOut eProcurement
Używając zewnętrznych katalogów w elektronicznym systemie zaopatrzenia z dynamicznie dostępnym katalogiem dostawcy, nie trzeba przechowywać informacji o produktach dostawców we własnych danych użytkownika. Zamiast tego koszyk w witrynie internetowej dostawcy jest konwertowany na wiersze zapotrzebowania zawierające poprawne informacje o produktach. 

Należy unikać utrzymywania opisów i cen produktów dostawców wśród własnych danych głównych produktów. Zamiast tego należy używać zewnętrznych katalogów w scenariuszu elektronicznego systemu zaopatrzenia z dynamicznie dostępnym katalogiem dostawcy. Wtedy gdy pracownicy tworzą zapotrzebowania, mogą dynamicznie sięgnąć do witryny katalogu zewnętrznego dostawcy (innymi słowy opuszczają własny system i przechodzą do witryny dostawcy). Produkty dodane do koszyka w witrynie internetowej dostawcy mogą być następnie konwertowane na wiersze zapotrzebowania. W związku z tym otrzymujesz poprawne informacje o produktach: identyfikator produktu, nazwę, cenę itd.

Aby korzystać z zewnętrznych katalogów, pracownik musi utworzyć zapotrzebowania na stronie **Moje zapotrzebowania na zakup**.

Pracownik, który utworzył zapotrzebowanie, jest nazywany wystawcą zapotrzebowania. Wystawca może wykonywać następujące zadania:

Używanie akcji wiersza **Katalogi zewnętrzne** w celu otwarcia strony zawierającej wszystkie katalogi zewnętrzne dostępne dla określonego zleceniodawcy, kupującej firmy i przyjmującej jednostki operacyjnej.

W zależności od posiadanych uprawnień zmiana zleceniodawcy, kupującej firmy i przyjmującej jednostki operacyjnej. Zmiana tych wartości może powodować zmianę listy zewnętrznych katalogów dostępnych dla zleceniodawcy. Dostępne zewnętrzne katalogi zależą od obecnie aktywnych zasad zakupów w kupującej firmie lub przyjmującej jednostce operacyjnej. Zasady te mogą przyznawać lub blokować dostęp do określonych kategorii zaopatrzenia. Może to wpływać na listę zewnętrznych katalogów mapowanych na te kategorie zaopatrzenia.

Aby uzyskać więcej informacji o zasadach, zobacz [Zasady zakupów](../procurement/purchase-policies.md).

- Aby znaleźć zewnętrzne katalogi dla określonych kategorii zaopatrzenia, wpisz tekst w polu wyszukiwania katalogów.
- Aby dodać produkty z zewnętrznego katalogu dostawcy w witrynie internetowej dostawcy, kliknij zewnętrzny katalog. Następnie dodaj produkty do koszyka i sfinalizuj transakcję. Wiersze koszyka zostaną przeniesione do programu Microsoft Dynamics 365.

Jeśli istnieje wiele kategorii zaopatrzenia, wybierz odpowiednią kategorię zaopatrzenia przed dodaniem wierszy do zapotrzebowania.
Gdy wiersze zostaną dodane do zapotrzebowania, można dodać więcej wierszy bez korzystania z zewnętrznych katalogów. Alternatywnie możesz dodawać wiersze nadal z zewnętrznych katalogów.

Gdy zapotrzebowanie jest gotowe, użyj akcji **Przepływ pracy** > **Prześlij**, aby je wysłać do zatwierdzenia.

