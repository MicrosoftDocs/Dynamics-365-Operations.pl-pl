---
title: Dla wielu nagłówków pracy na jednym paragonie jest drukowana tylko jedna etykieta
description: Dla wielu nagłówków pracy na jednym paragonie jest drukowana tylko jedna etykieta.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8e11dc918eb3c9085018d15b43819522cc8bebe3
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026812"
---
# <a name="only-one-label-is-printed-for-multiple-work-headers-on-a-single-receipt"></a>Dla wielu nagłówków pracy na jednym paragonie jest drukowana tylko jedna etykieta

Numer artykułu z bazy wiedzy: 4614667

## <a name="symptoms"></a>Objawy

Dla tego samego docelowego numer identyfikacyjny jest tworzona wiele nagłówków pracy jako część jednego zdarzenia odbieranego w aplikacji magazynowej. Po otrzymaniu produktu jest jednak drukowana tylko jedna etykieta z numerami identyfikacyjnymi.

## <a name="resolution"></a>Rozdzielczość

System jest szybując tak jak zaprojektowany.

W bieżącym projekcie pojedyncza etykieta dla numeru identyfikacyjnych jest zawsze generowana, niezależnie od istniejącej liczby kombinacji nagłówka pracy i wiersza pracy. Wygenerowana etykieta zawiera informacje dotyczące tylko jednej kombinacji.

Aby pracować nad tym problemem, upewnij się, że tworzenie nagłówka pracy jest zawsze mapowane na tylko jeden docelowy numer identyfikacyjny.
