---
title: Planowanie z użyciem ujemnych ilości dostępnych zapasów
description: W tym temacie wyjaśniono sposób obsługi ujemnych wartości dostępnych zapasów podczas korzystania z optymalizacji planowania.
author: ChristianRytt
manager: AnnBe
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: ca12d13f7318f649cb1dbc0f7c3cf56502c9d3ea
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "3077491"
---
# <a name="planning-with-negative-on-hand-quantities"></a>Planowanie z użyciem ujemnych ilości dostępnych zapasów

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

Jeśli w systemie jest wyświetlana ujemna zagregowana ilość zapasów, aparat planowania traktuje ilość jako 0 (zero), aby uniknąć nadmiernej podaży. Oto, jak działa ta funkcja:

1. Funkcja optymalizacji planowania agreguje ilości dostępnych zapasów na najniższym poziomie wymiarów zapotrzebowania. (Jeśli na przykład *lokalizacja* nie jest wymiarem zapotrzebowania, funkcja optymalizacji planowania umożliwia agregowanie dostępnych ilości na poziomie *magazynu*.)
1. Jeśli zagregowana ilość dostępna na najniższym poziomie wymiarów zapotrzebowania jest ujemna, system zakłada, że ilość dostępnych zapasów wynosi w rzeczywistości 0 (zero).

> [!IMPORTANT]
> System planowania może być tylko tak dokładny, jak dane wejściowe. Jeśli dane wejściowe są niedokładne, ujemne rekordy dostępnych zapasów będą wskazywały, że informacje o zapasach w Microsoft Dynamics 365 Supply Chain Management nie są zsynchronizowane z rzeczywistym stanem. Z tego powodu wynik planowania będzie wadliwy. Aby uzyskać dokładny wynik planowania, należy zminimalizować liczbę rekordów pokazującą ujemną ilość dostępnych zapasów.

## <a name="example-1"></a>Przykład 1

Magazyn 13 jest konfigurowany w następujący sposób:

- **Kod objęcia świadczeniem:** Minimum/Maksimum.
- **Minimum:** 15 sztuk (szt.)
- **Maksymalnie:** 25 szt.

Najniższy poziom wymiarów zapotrzebowania to *magazyn*, a następujące ilości dostępnych zapasów są rejestrowane na poziomie *lokalizacji*:

- **Oddział 1, magazyn 13, Lokalizacja 1:** 20 szt.
- **Oddział 1, magazyn 13, Lokalizacja 2:** &minus;8 szt.

Z tego względu zagregowana ilość dostępnych zapasów dla magazynu 13 wynosi 12 szt. (= 20 szt. &minus; 8 szt.).

W takim przypadku aparat planowania korzysta z zagregowanej ilości 12 szt. dla magazynu 13.

Wynik jest planowanym zamówieniem o ilości 13 szt. (= 25 szt. &minus; 12 szt.) w celu ponownego wypełnienia magazynu 13 od 12 szt. do 25 szt.

## <a name="example-2"></a>Przykład 2

Magazyn 13 jest konfigurowany w następujący sposób:

- **Kod objęcia świadczeniem:** Minimum/Maksimum.
- **Minimum:** 15 szt.
- **Maksymalnie:** 25 szt.

Najniższy poziom wymiarów zapotrzebowania to *magazyn*, a następujące ilości dostępnych zapasów są rejestrowane na poziomie *lokalizacji*:

- **Oddział 1, magazyn 13, Lokalizacja 1:** 4 szt.
- **Oddział 1, magazyn 13, Lokalizacja 2:** &minus;8 szt.

Z tego względu zagregowana ilość dostępnych zapasów dla magazynu 13 to &minus;4 szt. (= 4 szt. &minus; 8 szt.). Innymi słowy, jest mniej niż 0 (zero).

W takim przypadku aparat planowania zakłada, że ilość dostępnych zapasów dla magazynu 13 wynosi 0 szt. zamiast &minus;4 szt.

Wynik jest planowanym zamówieniem o ilości 25 szt. (= 25 szt. &minus; 0 szt.) w celu ponownego wypełnienia magazynu 13 od 0 szt. do 25 szt.

## <a name="related-resources"></a>Powiązane zasoby

[Omówienie optymalizacji planowania](planning-optimization-overview.md)

[Rozpoczęcie optymalizacji planowania](get-started.md)

[Analiza dopasowywania optymalizacją planowania](planning-optimization-fit-analysis.md)

[Wyświetlanie dzienników historii i planowania planów](plan-history-logs.md)

[Anuluj planowanie pracy](cancel-planning-job.md)
