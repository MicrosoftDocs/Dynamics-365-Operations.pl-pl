---
title: "Hybrydowe zamówienia klienta"
description: "Zamówienie klienta hybrydowego jest jedno zamówienie, które zawiera produkty, które mogą być przenoszone ze Sklepu przez klienta, a także produktów, które będą pobierane lub wysłane później."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 1ddfc050cef94f4a31f5858b84c89eadfa726b95
ms.lasthandoff: 03/31/2017


---

# <a name="hybrid-customer-orders"></a>Hybrydowe zamówienia klienta

Zamówienie klienta hybrydowego jest jedno zamówienie, które zawiera produkty, które mogą być przenoszone ze Sklepu przez klienta, a także produktów, które będą pobierane lub wysłane później.

W usłudze Microsoft Dynamics 365 dla operacji - sprzedaż detaliczna, można wybrać albo wykonują wszystkie produkty lub przeprowadzenia wybranych produktów do zamówienia danego klienta. Produkt, który wiersze oznaczone jak przeprowadzać są automatycznie zafakturowane po utworzeniu zlecenia, podobnie to jest taka sama dla zamówienie, które ma być wyłapywane po utworzeniu zlecenia. Wysokość kwoty należnej na hybrydowe zamówień jest określana przez dodanie oprocentowanie lokaty na pobranie i linii produktów statku pełną kwotę przeprowadzą wierszy. Dla zamówień mieszańców można przełączać się między trybem zamówienia klienta i środków pieniężnych i własny transport w następujący sposób:

-   Jeżeli wszystkie produkty w koszyku są ustawione na **przeprowadzenia dostawy**, kolejność będzie obsługiwany jako transakcja środków pieniężnych i własny transport.
-   Jeśli wszystkie linie w koszyku jest ustawiony na **pobrania** lub **statek dostawy**, kolejność będzie obsługiwany jako transakcja zamówienia odbiorcy.

Po zaznaczeniu wiersza koszyka i **wybierz zaznaczone**, **statek zaznaczone**, lub **przeprowadzać wybranego** jest zaznaczona, tylko wiersz określonego koszyka jest ustawiona z tej metody dostawy. W takim przypadku przepływ dalszych operacji jest kontynuowane w zwykły sposób. Jednak jeśli **wybierz zaznaczone**, **statek zaznaczone**, lub **przeprowadzić wybranego** jest zaznaczona bez wiersza koszyka zaznaczone, otwiera nową stronę, które są wyświetlane wszystkie wiersze koszyka. Na tym ekranie można wybrać wiele wierszy naraz do ustawiania metody dostawy. Użycie tej metody do zaznaczania wierszy, zostaną zastąpione wszystkie poprzednie metody dostawy, przypisany do wiersza.

<a name="see-also"></a>Informacje dodatkowe
--------

[Omówienie zamówień klienta](customer-orders-overview.md)


