---
title: Omówienie modułu Zarządzanie rabatami
description: Ten temat zawiera omówienie modułu Zarządzanie rabatami dla Microsoft Dynamics 365 Supply Chain Management.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 13c40566f0842360cd730b0578b665fa3646344d
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687448"
---
# <a name="rebate-management-module-overview"></a>Omówienie modułu Zarządzanie rabatami

[!include [banner](../includes/banner.md)]

Moduł **Zarządzanie rabatami** umożliwia tworzenie umów, umów lub umów zawieranych między firmą a jej klientami lub dostawcami, w celu obliczania rabatów, potrąceń i tantiem. Zarządzanie rabatami śledzi i obsługuje transakcje rabatów i potrąceń w lokalizacji centralnej, gdzie użytkownicy mogą efektywnie tworzyć, przeglądać i przetwarzać.

Zarządzanie rabatami umożliwia tworzenie, obsługę i przetwarzanie *rabatów*. Rabat to zwrot części ceny zakupu przez sprzedającego lub kupca. Rabaty są zwykle oparte na zakupie określonej ilości lub wartości towarów w danym okresie. W odróżnieniu od rabatów rabaty są wykonywane po w pełni zafakturowana kwota zakupu.

Zarządzanie rabatami obsługuje również *potrącenia*. Potrącenie to wynagrodzenie, wynagrodzenie lub opłata płacona za licencję lub prawo do korzystania z własności intelektualnej, takiej jak marka, prawa autorskie lub patent, albo uprawnienie do korzystania z zasobów do celów, takich jak nazwa, struktura lub wyszukiwanie. Potrącenia są zwykle obliczane jako procent przychodu lub zysku ze zrealizowanego użytkowania. Im więcej jest używanych własności intelektualnej lub zasobów naturalnych, tym większe jest zrealizowane potrącenie.

Ponadto zarządzanie rabatami obsługuje *tantiemy* odbiorcy. Tantiemy to płatności dokonywane przez jedną stronę na rzecz licencji lub tantiemy na rzecz prawa do używania środka trwałego.

Zarządzanie rabatami umożliwia definiowanie profilów księgowania dotyczących aprowizacji, rabatów i odpisów. Ponadto księgowania mogą być zdefiniowane dla określonego odbiorcy lub dostawcy. W ten sposób transakcje, które nie mają zastosowania do wszystkich scenariuszy odbiorcy lub dostawcy, mogą być śledzone za pomocą księgowania.

Transakcje rabatowe są generowane automatycznie na podstawie metody obliczania wybranej i zaplanowanej w zadaniach wsadowych. Dodatkowo można skonfigurować przepływy pracy, aby zarządzać umowami, przeglądać je i zatwierdzać.

## <a name="basis-calculation"></a>Podstawowe obliczanie

Rabaty dla odbiorcy, tantiemy dla odbiorcy i rabaty dostawcy mogą korzystać z różnych podstaw, w zależności od wymagań firmy:

- Rabaty dla odbiorcy mogą być oparte na zamówieniach sprzedaży, fakturach lub fakturach.
- Tantiemy dla odbiorcy mogą być oparte na zamówieniach sprzedaży, fakturach lub opłaconych fakturach.
- Rabaty dostawcy mogą być oparte na zamówieniach zakupu lub sprzedaży. Wartości te można obliczać na podstawie produktów zakupionych od dostawcy rabatu i sprzedawanych klientom na podstawie faktur sprzedaży.

## <a name="flexible-calculations"></a>Obliczanie elastyczne

Okresy obliczania rabatów są dostępne zarówno w przypadku umów odbiorcy, jak i transakcji dostawcy. Okres obliczania określa długość umowy, częstotliwość obliczania oraz okres obliczania. Rabaty mogą być naliczane na podstawie ilości w zamówieniu sprzedaży lub kwot dla produktów kwalifikowanych w okresie rabatowym.

Dla każdego obliczenia umowy można ustawić dowolny z następujących okresów:

- Faktura VAT
- Dzień
- Tydzień
- Miesiąc
- Kwartał
- Rok
- Okres dostosowany
- Dowolna wielokrotność dowolnego z uprzednio wymienionych okresów

Obliczenia mogą być stosowane do pojedynczych odbiorców i produktów, grup odbiorców i produktów lub wszystkich odbiorców i produktów. Rabaty z wieloma szczegółami mogą mieć różne zakresy kwalifikacji. Okresy rezerwy i roszczenia mogą się różnić. Na przykład warunki mogą być przetwarzane codziennie, podczas gdy roszczenia są przetwarzane raz w miesiącu.

Rabaty można konfigurować na podstawie wielu różnych parametrów. Można je na przykład skonfigurować jako wartość procentową, stawkę lub stałą kwotę. Istnieją cztery główne metody obliczania:

- Zajęta
- Skumulowana wartość
- Kroczące
- Wartość całkowita

Wyniki obliczeń rabatów mogą być również pomniejszane o inne rabaty, w zależności od tego, czy rabat jest ustawiony do obliczania na podstawie kwoty netto.

Ze strony dostawcy rabaty oparte na zamówieniach sprzedaży mogą obliczać cenę na podstawie reguły FIFO, ostatniej ceny zakupu, średniej ceny zakupu lub ceny sprzedaży.

## <a name="rebate-target-transactions"></a>Transakcje docelowe rabatu

Wyniki wygenerowane przez umowę rabatową lub umowę rabatową mogą być finansami lub pozycjami.

Wyniki finansowe są określane na podstawie typu płatności przypisanego do umowy z profilu księgowania. Te dane wyjściowe mogą obejmować arkusze potrąceń od odbiorcy, faktury tekstowe i faktury dostawcy. Na potrzeby inspekcji finansowe transakcje docelowe rabatów obejmują odwołanie do pochodzących umów rabatowych.

Wyjścia towarów tworzy bezpłatne zamówienie sprzedaży pozycji dla rabatów dla odbiorcy oraz zamówienie zakupu dla rabatów dostawcy. Transakcje docelowe rabatów dla pozycji zawierają opcje służące do określania, które odwołanie do rabatu powinno zostać wprowadzone w zamówieniu sprzedaży lub zakupu pozycji wolnej.

## <a name="accurate-rebate-calculations"></a>Dokładne obliczenia rabatów

Dokładność i dokładność obliczeń rabatów zależy od kombinacji powiązanych transakcji, częstotliwości obliczeń, podstawy obliczania oraz wybranej metody obliczania. Rezerwy na rabaty mogą służyć do naliczania wartości zaksięgowanych i roszczeń.

Rezerwy mogą być zarządzane codziennie, tygodniowo, miesięcznie lub według niestandardowego okresu. Jednakże funkcjonalność może przydzielać lub wypłacać rabat, lub otrzymywać jego wypłatę, z dowolną określoną częstotliwością, która jest taka sama lub dłuższa niż częstotliwość dostarczania. Odpis korzysta z tej samej częstotliwości co rabat. Użytkownicy mogą w dowolnym momencie skorygować plan lub kwoty płatności.

Użytkownicy nie muszą już obsługiwać transakcji lub aprowizacji w dwóch krokach. Aprowizacje i odpisy są księgowane bezpośrednio w księdze. Ponadto faktury korygowane mogą być tworzone automatycznie. W związku z tym istnieje pełna integracja z rozrachunkami z dostawcami i rozrachunkami z odbiorcami. Podczas przetwarzania obliczenia mogą uwzględniać rabaty rozliczenie, zapłacone faktury, rabaty handlowe i istniejące faktury korygujące, aby zagwarantować dokładne obliczenie kwot i wartości.

Podczas obliczania rabatów proces tworzy transakcje, które można przeglądać przed zaksięgowaniem. W odrębnym procesie księgowane są transakcje związane z zarządzaniem rabatami. Dziennik, nota uznaniowa lub transakcja obciążeniowa mogą być następnie utworzone podczas księgowania proponowanych transakcji. Raporty i listy transakcji można uzyskać w celu zapewnienia zgodności, efektywności i przezroczystości.

## <a name="guaranteed-royalty-payments"></a>Gwarantowane płatności tantiem

W zarządzaniu rabatami funkcja automatycznego generowania płatności umożliwia szybkie i łatwe obsługę tantiem, nawet jeśli mają zastosowanie wymagane minimum.

## <a name="maximizing-spend-versus-rebates"></a>Maksymalizowanie wydatków w porównaniu z rabatami

Dostawcy i produkty mogą być pogrupowane według terytorium i można dostarczać różne oferty, w zależności od kraju lub regionu transakcji. Po wybraniu produktów użytkownicy mogą zdefiniować uwzględnione towary oraz liczbę towarów, które zostaną użyte w rozliczeniu rabatu.
