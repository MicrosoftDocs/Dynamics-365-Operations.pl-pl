---
title: Sprzedaż i zwrot produktów nienależących do asortymentu sklepu
description: W aplikacji Dynamics 365 Commerce można sprzedawać i zwracać produkty spoza asortymentu.
author: pdp1207
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: prabhup
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 86c6ecf9ef67ca3ac4ed3c44d930acaa965112b6
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023701"
---
# <a name="sell-and-return-products-that-arent-part-of-a-stores-assortment"></a>Sprzedaż i zwrot produktów nienależących do asortymentu sklepu

[!include [banner](includes/banner.md)]

Typowy scenariusz u każdego sprzedawcy detalicznego to sprzedaż produktów klientom lub przyjmowanie zwrotów od klientów, nawet jeśli sprzedawcy nie mają tych produktów w sklepie (innymi słowy produkty nie wchodzą w skład asortymentu sklepu).

Poniżej przedstawiono niektóre typowe scenariusze:

+ Sprzedawca detaliczny nie posiada wszystkich swoich produktów w określonym sklepie. Pozostałe produkty są przechowywane w magazynie. Pracownik sklepu może pomóc klientowi, wyszukując lub przeglądając produkty w magazynie, dodając je do koszyka, a następnie finalizując transakcję przez wybranie metody dostawy, takiej jak wysyłka na podany adres z magazynu lub osobisty odbiór produktu przez klienta z bieżącego sklepu lub z innego sklepu.
+ Sprzedawca nie ma określonych produktów w sklepie lub nie ma ich w sklepie odwiedzonym przez klienta, ale produkty są dostępne w innych sklepach. Pracownik sklepu może pomóc klientowi, wyszukując lub przeglądając produkty w sklepie, dodając je do koszyka, a następnie finalizując transakcję przez wybranie metody dostawy.
+ Sprzedawca detaliczny ma wiele sklepów w danym mieście lub regionie i nie chce zmuszać klientów, aby zwracali produkty do tego samego sklepu, w którym je kupili. Zamiast tego klienci mogą zwracać produkty do dowolnych sklepów.

Te typowe scenariusze są dostępne dla sprzedawców detalicznych używających usługi Commerce. Aplikacja Commerce oferuje następujące możliwości:

+ Wyszukiwanie lub przeglądanie produktów w innych sklepach.
+ Wyszukiwanie lub przeglądanie wszystkich zwolnionych produktów.
+ Tworzenie transakcji zapłaty przy kasie i wychodzenia z produktami ze sklepu lub tworzenie zamówień odbiorców.
+ Wybieranie opcji dostawy dla zamówień odbiorców.
+ Odbiór produktów w bieżącym sklepie lub innym sklepie.
+ Anulowanie zamówienia w bieżącym sklepie lub innym sklepie.
+ Zwrot zamówionych towarów z paragonem lub bez w bieżącym lub innym sklepie.
