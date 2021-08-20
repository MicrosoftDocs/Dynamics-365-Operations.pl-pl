---
title: Fizycznie odebrane zamówienia zakupu nie są widoczne w raporcie zamknięcia magazynu
description: Fizycznie otrzymane zamówienia zakupu nie pojawiają się w raporcie zamknięcia zapasów Sprawdź otwarte ilości.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventOpenQtyCritical
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 49faa2c68d496c5c0d8c7e4abfd93d9a917857220dd23c09a050fa3436e1d49a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746874"
---
# <a name="physically-received-purchase-orders-dont-appear-on-the-inventory-closing-report"></a>Fizycznie odebrane zamówienia zakupu nie są widoczne w raporcie zamknięcia magazynu

Numer artykułu z bazy wiedzy: 4612595

## <a name="symptoms"></a>Objawy

Fizycznie otrzymane zamówienia zakupu nie pojawiają się w raporcie zamknięcia zapasów **Sprawdź otwarte ilości**.

## <a name="resolution"></a>Rozdzielczość

Raport **Sprawdź otwarte ilości** zawiera transakcje rozliczeń, których nie można rozliczyć względem finansowo zaktualizowanych przychodów magazynowych dla wybranej daty zamknięcia. Można wybrać opcję uwzględniania w raporcie fizycznego przychodu. W takim przypadku fizyczne przychody zostaną wyświetlone, jeśli będą pokrywały transakcje rozliczeniowe, których nie można rozliczyć. Aby uzyskać więcej informacji, zobacz [Przygotowanie do przeprowadzenia zamknięcia magazynu](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).
