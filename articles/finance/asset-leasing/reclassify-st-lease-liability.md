---
title: Zmienianie klasyfikacji krótkoterminowej części zobowiązania z tytułu wynajmu
description: W tym artykule opisano sposób tworzenia miesięcznego wpisu w arkuszu w celu przeklasyfikowania części zobowiązania z tytułu wynajmu na krótkoterminowe.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7c7c3f86aa5d24e9aeed89526a4b7317699e9a78
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886350"
---
# <a name="reclassify-the-short-term-portion-of-lease-liability"></a>Zmienianie klasyfikacji krótkoterminowej części zobowiązania z tytułu wynajmu

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób tworzenia miesięcznego wpisu w arkuszu w celu przeklasyfikowania części zobowiązania z tytułu wynajmu na krótkoterminowe. Jeśli harmonogramem wybranym w procesie wsadowym jest **Przeklasyfikowanie krótkoterminowego zobowiązania z tytułu wynajmu**, jest tworzony wpis w arkuszu. Ten wpis służy do księgowania bieżącej części zobowiązania z tytułu wynajmu w ostatnim dniu miesiąca. W tym samym czasie jest księgowany wpis stornujący na pierwszy dzień następnego miesiąca.

Krótkoterminowa część zobowiązania z tytułu wynajmu jest wyświetlana w harmonogramie amortyzacji zobowiązań. Po zaksięgowaniu wpisu w arkuszu staje się dostępna kolumna **Utworzono arkusz przeklasyfikowania zobowiązania**, a w harmonogramie jest wpisywany identyfikator arkusza.

Aby utworzyć i zaksięgować wpis w arkuszu dotyczący przeklasyfikowania zobowiązania krótkoterminowego, należy wykonać następujące kroki.

1. Przejdź do **Wynajem składnika majątku \> Okresowe \> Tworzenie arkusza w partii**.
2. W oknie dialogowym **Tworzenie arkusza w partii** w polu **Wybierz harmonogram** wybierz pozycję **Przeklasyfikowanie krótkoterminowego zobowiązania z tytułu wynajmu**.
3. W polu **Grupa wynajmu** wybierz grupę wynajmu. Alternatywnie w polu **Identyfikator księgi** wybierz identyfikator księgi.
4. Włącz parametr **Księguj**. Alternatywnie, jeśli wpis powinien zostać utworzony, ale nie zaksięgowany, pozostaw ten parametr wyłączony.
5. Kliknij przycisk **OK**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
