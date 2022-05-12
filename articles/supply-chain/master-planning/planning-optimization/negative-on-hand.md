---
title: Planowanie z użyciem ujemnych ilości dostępnych zapasów
description: W tym temacie wyjaśniono sposób obsługi ujemnych wartości dostępnych zapasów podczas korzystania z optymalizacji planowania.
author: t-benebo
ms.date: 07/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: bb837a38485bad2b9b76a5e4f20d311c0281e192
ms.sourcegitcommit: 1050e58e621d9a0454895ed07c286936f8c03320
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2022
ms.locfileid: "8625393"
---
# <a name="planning-with-negative-on-hand-quantities"></a>Planowanie z użyciem ujemnych ilości dostępnych zapasów

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

## <a name="planning-when-there-is-a-reservation-against-negative-on-hand-inventory"></a>Planowanie w przypadku rezerwacji względem ujemnych dostępnych zapasów

Jeśli dostosujesz zapasy, gdy istnieją rezerwacje fizyczne, możesz spowodować sytuację, w której zamówienie jest fizycznie zarezerwowane dla ujemnych zapasów. W tym przypadku, ponieważ istnieje fizyczna rezerwacja, musisz mieć zapas, który pokryje zarezerwowaną ilość. W związku z tym konieczne jest uzupełnienie zapasów, więc system albo utworzy planowane zamówienie na uzupełnienie ilości, która nie może być pokryta z istniejących zapasów, albo pokryje ją z istniejącego zamówienia na daną pozycję.

Poniższy przykład ilustruje ten scenariusz.

### <a name="example"></a>Przykład

System jest skonfigurowany w następujący sposób:

- Produkt *FG* istnieje i ma *10* szt. dostępnych zasobów.
- Konfiguracja produktu pozwala na fizyczne ujemne zapasy.
- Zamówienie sprzedaży istnieje dla ilości *10* szt. produktu *FG*.
- Ilość zamówienia sprzedaży jest fizycznie zarezerwowana na istniejące dostępne zapasy.

Następnie można dostosować ilość produktu *FG* tak, aby dostępne zapasy miały 5. Ponieważ stan zapasów produktów w magazynie wynosi 5, ilość zamówienia sprzedaży jest teraz zarezerwowana dla ilości, która nie jest dostępna w magazynie (podobnie byłoby, gdyby stan zapasów w magazynie wynosił 0, wtedy zamówienie sprzedaży byłoby zarezerwowane dla ujemnego stanu zapasów). Jeśli uruchomisz teraz planowanie główne, zostanie utworzone planowane zamówienie na ilość 5 dla *FG* w celu dostarczenia zamówienia sprzedaży, ponieważ Optymalizacja Planowania zawsze wykorzysta istniejące dostawy lub utworzy nowe planowane zamówienie w celu dostarczenia fizycznej rezerwacji.

## <a name="related-resources"></a>Powiązane zasoby

- [Omówienie optymalizacji planowania](planning-optimization-overview.md)
- [Rozpoczęcie optymalizacji planowania](get-started.md)
- [Analiza dopasowywania optymalizacją planowania](planning-optimization-fit-analysis.md)
- [Wyświetlanie dzienników historii i planowania planów](plan-history-logs.md)
- [Anuluj planowanie pracy](cancel-planning-job.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
