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
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9259c9bbf52c1c09a7092db6976fc3fabca6601
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990446"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]