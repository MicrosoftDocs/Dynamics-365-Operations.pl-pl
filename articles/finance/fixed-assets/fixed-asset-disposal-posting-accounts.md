---
title: Konta księgowania likwidacji środków trwałych
description: W tym temacie wyjaśniono, jak w księdze głównej skonfigurować konta księgowania operacji likwidacji środków trwałych.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: kfend
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8501bbb0fc47fb52e100d9086054db4831dae178
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/06/2022
ms.locfileid: "8720259"
---
# <a name="fixed-asset-disposal-posting-accounts"></a>Konta księgowania likwidacji środków trwałych

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak w księdze głównej skonfigurować konta księgowania podczas operacji likwidacji środków trwałych.

Aby skonfigurować konta księgowania w księdze głównej do użycia podczas likwidacji środka trwałego, wybierz opcję **Likwidacja — sprzedaż** i **Likwidacja — odpadki** na skróconej karcie **Konta księgi**, na stronie **Profile księgowania środków trwałych**.

Dla obu typów transakcji (likwidacja środka trwałego przez sprzedaży lub pozbycie się) na konto księgowe wpływa wartość likwidacji środka trwałego. Księgowanie po stronie debetowej obciąży konto przeciwstawne, którym może być konto bankowe (jako przykład). Jeśli środek trwały zostanie sprzedany odbiorcy, zamiast konta przeciwstawnego użyte zostanie konto odbiorcy. Aby uzyskać więcej informacji, zobacz temat [Likwidacja środków trwałych uznanych za odpadki](dispose-of-a-fixed-asset-as-scrap.md).

Kliknij **Likwidacja**, kliknij **Sprzedaż** lub **Odpadki**, a następnie skonfiguruj szczegóły kont, aby wycofać wartość księgową netto środka trwałego. Można również wprowadzić informacje w polach **Księguj wartość** i **Typ wartości sprzedaży** na stronie **Parametry likwidacji**. 

Transakcja likwidacji środka trwałego w puli środków trwałych o niskiej wartości zmniejsza wartość księgową netto tej puli tylko o kwotę danej likwidacji. Jeśli jednak wartość sprzedaży takiego środka trwałego przekracza wartość księgową netto wspomnianej puli, wartość księgowa netto zostanie zmniejszona do zera.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
