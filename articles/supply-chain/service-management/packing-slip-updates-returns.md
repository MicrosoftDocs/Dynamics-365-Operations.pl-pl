---
title: Aktualizowanie dokumentów dostawy w związku ze zwrotami
description: Aby zwrócone towary mogły zostać przyjęte do magazynu, najpierw trzeba zaktualizować dokument dostawy dla zamówienia, do którego one należą.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPackingSlipJournalHistory, SalesParmPackingSlipTrackingInformation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a9b5c7e5726c36aa963e5750c63df20c1e2e6c35
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810709"
---
# <a name="packing-slip-updates-for-returns"></a>Aktualizowanie dokumentów dostawy w związku ze zwrotami  

[!include [banner](../includes/banner.md)]


Aby zwrócone towary mogły zostać przyjęte do magazynu, najpierw trzeba zaktualizować dokument dostawy dla zamówienia, do którego one należą. Podobnie jak proces aktualizacji faktury jest aktualizacją transakcji finansowej, tak proces aktualizacji dokumentu dostawy jest fizyczną aktualizacją rekordu zapasów, tzn. zatwierdza zmiany w zapasach. W przypadku zwrotów kroki przypisane do akcji dyspozycji są implementowane podczas aktualizacji dokumentu dostawy.

Aktualizację dokumentu dostawy można przetworzyć w arkuszu przyjęcia towaru lub zamówieniu zwrotu.

W trakcie procesu księgowania dokumentów dostawy numer odwołania dokumentu dostawy z dokumentów wysyłki odbiorcy można skojarzyć z wierszami zamówienia. To skojarzenie jest opcjonalne i ma charakter wyłącznie informacyjny. Nie tworzy żadnych aktualizacji transakcji.

Jeśli nie wszystkie oczekiwane towary do zwrotu nadejdą, w aktualizacji dokumentu dostawy należy uwzględnić tylko ilość przyjętą. Pozostałe towary należy pozostawić w zamówieniu, dopóki nie nadejdzie reszta wysyłki zwrotu.

Ponadto jeśli towar zostanie odesłany z kwarantanny do działu wysyłek i przyjęć, na przykład w przypadku, gdy inspektor kwarantanny nie wie, gdzie ma być przechowywany towar w zapasach, należy zaktualizować odpowiedni dokument dostawy, aby poprawnie zarejestrować i obsługiwać kod dyspozycji określony w wyniku kwarantanny.

Podczas aktualizacji dokumentu dostawy dla towaru zwróconego na podstawie umowy sprzedaży zobowiązanie umowy sprzedaży dla tego towaru jest automatycznie aktualizowane, aby odzwierciedlało zmianę ilości lub kwoty. 

## <a name="see-also"></a>Informacje dodatkowe

[Aktualizowanie faktur w związku ze zwrotami](perform-invoice-updates-for-returns.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]