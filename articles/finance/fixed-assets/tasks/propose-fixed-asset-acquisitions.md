---
title: Proponowanie nabycia środka trwałego
description: W tym temacie pokazano sposób nabywania środka trwałego przy użyciu propozycji nabycia zdefiniowanej w arkuszu środków trwałych.
author: saraschi2
manager: AnnBe
ms.date: 07/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0997af638c141661afb677e2407a90a883168aed
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446654"
---
# <a name="propose-fixed-asset-acquisitions"></a>Proponowanie nabycia środka trwałego

[!include [banner](../../includes/banner.md)]

W tym temacie pokazano sposób nabywania środka trwałego przy użyciu propozycji nabycia zdefiniowanej w arkuszu środków trwałych. Procedura korzysta z roli księgowego i danych firmy demonstracyjnej USMF. Aby nabyć środek trwały za pośrednictwem arkusza propozycji środków trwałych, należy najpierw utworzyć rekord środka trwałego, a następnie zdefiniować cenę nabycia w księdze składników majątku.

1. W okienku nawigacji przejdź do **Moduły > Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych**.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa** wprowadź lub wybierz wartość.
4. W okienku akcji wybierz **Wiersze**.
5. Wybierz **Propozycje**.
6. Wybierz **Propozycja nabycia**.
7. Wybierz **Filtry**. Wybierz **Resetuj**, aby wyczyścić poprzednie wartości.
8. Zaznacz wiersz **Numer środka trwałego**.
9. W polu **Kryteria** wprowadź lub wybierz wartość. Skonfiguruj pozostałe kryteria środków trwałych, które chcesz nabyć za pomocą tej propozycji.  
10. Wybierz dwa razy **OK**, aby wyjść z okienka.
- Sprawdź utworzone wiersze transakcji.  
- W propozycji nabycia zostaną uwzględnione tylko środki trwałe, które w księdze mają ustawioną datę nabycia i cenę nabycia.  
11. Na stronie wybierz kartę **Księgi**.
12. Wybierz opcję **Zaksięguj**.
