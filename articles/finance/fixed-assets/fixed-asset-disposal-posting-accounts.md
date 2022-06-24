---
title: Konta księgowania likwidacji środków trwałych
description: W tym artykule wyjaśniono, jak w księdze głównej skonfigurować konta księgowania operacji likwidacji środków trwałych.
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
ms.openlocfilehash: 1272cdb16396d24b5495f023e7b9fe3dee341507
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871341"
---
# <a name="fixed-asset-disposal-posting-accounts"></a>Konta księgowania likwidacji środków trwałych

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak w księdze głównej skonfigurować konta księgowania podczas operacji likwidacji środków trwałych.

Aby skonfigurować konta księgowania w księdze głównej do użycia podczas likwidacji środka trwałego, wybierz opcję **Likwidacja — sprzedaż** i **Likwidacja — odpadki** na skróconej karcie **Konta księgi**, na stronie **Profile księgowania środków trwałych**.

Dla obu typów transakcji (likwidacja środka trwałego przez sprzedaży lub pozbycie się) na konto księgowe wpływa wartość likwidacji środka trwałego. Księgowanie po stronie debetowej obciąży konto przeciwstawne, którym może być konto bankowe (jako przykład). Jeśli środek trwały zostanie sprzedany odbiorcy, zamiast konta przeciwstawnego użyte zostanie konto odbiorcy. Aby uzyskać więcej informacji, zobacz temat [Likwidacja środków trwałych uznanych za odpadki](dispose-of-a-fixed-asset-as-scrap.md).

Kliknij **Likwidacja**, kliknij **Sprzedaż** lub **Odpadki**, a następnie skonfiguruj szczegóły kont, aby wycofać wartość księgową netto środka trwałego. Można również wprowadzić informacje w polach **Księguj wartość** i **Typ wartości sprzedaży** na stronie **Parametry likwidacji**. 

Transakcja likwidacji środka trwałego w puli środków trwałych o niskiej wartości zmniejsza wartość księgową netto tej puli tylko o kwotę danej likwidacji. Jeśli jednak wartość sprzedaży takiego środka trwałego przekracza wartość księgową netto wspomnianej puli, wartość księgowa netto zostanie zmniejszona do zera.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
