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
ms.openlocfilehash: 9508d6d75d8ebee7ca10140ed4c4215d7ad1dda7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026813"
---
# <a name="physically-received-purchase-orders-dont-appear-on-the-inventory-closing-report"></a>Fizycznie odebrane zamówienia zakupu nie są widoczne w raporcie zamknięcia magazynu

Numer artykułu z bazy wiedzy: 4612595

## <a name="symptoms"></a>Objawy

Fizycznie otrzymane zamówienia zakupu nie pojawiają się w raporcie zamknięcia zapasów **Sprawdź otwarte ilości**.

## <a name="resolution"></a>Rozdzielczość

Raport **Sprawdź otwarte ilości** zawiera transakcje rozliczeń, których nie można rozliczyć względem finansowo zaktualizowanych przychodów magazynowych dla wybranej daty zamknięcia. Można wybrać opcję uwzględniania w raporcie fizycznego przychodu. W takim przypadku fizyczne przychody zostaną wyświetlone, jeśli będą pokrywały transakcje rozliczeniowe, których nie można rozliczyć. Aby uzyskać więcej informacji, zobacz [Przygotowanie do przeprowadzenia zamknięcia magazynu](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).
