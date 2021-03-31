---
title: Księgowanie wpisów w arkuszu dotyczących korekt przejścia w module Wynajem składnika majątku
description: W tym temacie opisano funkcję, która umożliwia przeniesienie portfela umów wynajmu do nowych standardów księgowania takich umów — Accounting Standards Codification Topic 842 (ASC 842) i Międzynarodowy Standard Sprawozdawczości Finansowej nr 16 (MSSF 16).
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7ed62f52753a6697a7547ada0317041669cf3506
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207212"
---
# <a name="post-transition-adjustment-journal-entries-in-asset-leasing"></a>Księgowanie wpisów w arkuszu dotyczących korekt przejścia w module Wynajem składnika majątku

[!include [banner](../includes/banner.md)]

W tym temacie opisano funkcję, która umożliwia przeniesienie portfela umów wynajmu do nowych standardów księgowania takich umów — Accounting Standards Codification Topic 842 (ASC 842), który jest standardem przyjętym w ogólnie przyjętych zasadach rachunkowości w Stanach Zjednoczonych (US GAAP), i Międzynarodowy Standard Sprawozdawczości Finansowej nr 16 (MSSF 16).

Aby uzyskać informacje dotyczące konfigurowania księgi dla przejścia do nowych standardów, zapoznaj się z tematem [Konfigurowanie ksiąg wynajmu](set-up-lease-books.md).

Podczas tworzenia wpisu w arkuszu dotyczącego korekty przejścia jest tworzony wpis w arkuszu. Ten wpis odzwierciedla wpływ zarejestrowania wynajmu na bilans według nowych standardów na dany dzień. W tym dniu odpowiednie konto aktywów jest obciążane wartością bilansową, a konto pasywów jest uznawane. Różnica jest księgowana po stronie debetowej lub kredytowej na koncie zysków zatrzymanych.

Aby zaksięgować korektę przejścia zgodnie z nowymi standardami rachunkowości, wykonaj następujące kroki.

1. Na stronie **Podsumowanie wynajmu** wybierz wynajem, a następnie wybierz opcję **Księgi**.
2. W księdze wybierz opcję **Harmonogram płatności**.
3. W oknie dialogowym **Harmonogram płatności** wybierz opcję **Potwierdź**. Następnie zamknij okno dialogowe.
4. Wybierz opcję **Korekta przejścia**.

    > [!NOTE]
    > Korektę przejścia można utworzyć tylko dla ksiąg wynajmu przypisanych do księgi mającej dostępne pole **Księga przejścia**. Jeśli data w polu **Rozpoczęcie wynajmu** jest późniejsza niż data przejścia, wartość w polu **Korekta przejścia** nie zostanie zaktualizowana.

5. Aby wyświetlić wpis w arkuszu, wybierz opcję **Arkusze wynajmu składnika majątku**.
6. Zaznacz nowy arkusz, a następnie wybierz opcję **Księguj**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]