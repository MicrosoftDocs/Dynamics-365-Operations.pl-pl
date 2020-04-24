---
title: Księgowanie produkcji
description: Ten artykuł zawiera informacje o różnych typach księgowań w procesie produkcji.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventItemGroup, ProjCategory, WrkCtrResourceGroup, WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 54591
ms.assetid: 0917fe64-f643-46ae-98ff-5013b266a067
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 20a94ed3c64e81013edfa10e060dd32e04d12577
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214488"
---
# <a name="production-posting"></a>Księgowanie produkcji

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o różnych typach księgowań w procesie produkcji.

Działania księgowania produkcji są wykonywane po procesach produkcyjnych, które zostały opisane w poniższych sekcjach.

## <a name="material-consumption"></a>Zużycie materiału
Materiały są rejestrowane jako zużyte w trakcie produkcji, gdy księgowany jest arkusz listy pobrania produkcji. Ten proces generuje transakcje rozchodu, które odliczają dostępne zapasy. W parametrach produkcji można określić, czy wartość surowców będących w toku (Praca w toku \[WIP\]) ma być księgowane w księdze. Wartość surowców, które są w toku (PWT), jest następnie księgowana na dedykowanym koncie listy pobrania i dedykowanym koncie przeciwstawnym.

## <a name="time-consumption"></a>Zużycie czasu
Czas, jaki pracownicy poświęcają na realizację zadań związanych z produkcją, jest rejestrowany w arkuszu Karta marszruty lub Karta zadań. Te arkusze są księgowane na specjalnym koncie dla zasobów będących w toku (PWT). Takie księgowanie pokazuje czas realizacji zlecenia produkcyjnego. Po zarejestrowaniu zlecenia produkcyjnego jako zakończonego konta PWT są rozliczane.

## <a name="reporting-finished-goods-and-error-quantities"></a>Zgłaszanie gotowych wyrobów i ilości błędów
Gdy zlecenie produkcyjne zostanie zgłoszone jako zakończone, ilość wyprodukowanych towarów, które zostały zakończone, jest aktualizowana w module Zarządzanie zapasami za pomocą arkusza Zgłoszenie wyrobów gotowych. Jeśli używasz księgowania pracy w toku (PWT), co można ustawić w parametrach produkcji, w arkuszu księgi następuje zmniejszenie kont PWT i zwiększenie zapasów produktów gotowych. Arkusz używa standardowego kosztu, który jest zdefiniowany dla produktu.

## <a name="ending-the-production-order"></a>Kończenie zlecenia produkcyjnego
Przed zakończeniem zlecenia produkcyjnego obliczane są rzeczywiste koszty dla wyprodukowanej ilości. Wszystkie szacowane koszty materiałów, robocizny i narzutów zostają wycofane i zastąpione kosztami rzeczywistymi. Całkowity koszt gotowego towaru księgowany jest po stronie debetowej z konta Przychody oraz po stronie debetowej na koncie Rozchody. Jeśli w momencie uruchamiania obliczenia kosztów jest zaznaczone pole wyboru **Zakończ zadanie**, stan zlecenia produkcyjnego zmienia się na **Zakończone**. Ten stan zapobiega przypadkowemu zaksięgowaniu dodatkowych kosztów dla ukończonego zlecenia produkcyjnego. Można określić, że wartość ilości błędnych towarów zgłaszana w trakcie zgłaszania wyrobów gotowych powinna być alokowana do ilości dobrych towarów, które zostały zgłoszone jako gotowe. Można też określić, że ilość błędów powinna być księgowana na specjalnym koncie odpadków.

## <a name="controlling-the-level-of-ledger-posting"></a>Kontrolowanie poziomu księgowania w księdze
W **Parametrach kontroli produkcji** można użyć pola **Księgowanie w księdze**, aby ustawić poziom księgowania w księdze dla procesów produkcyjnych. Dostępne są następujące wartości:

-   **Towar i zasób** — pozwala używać kont księgowych, które zostały skonfigurowane w grupach towarów dla surowców i wyrobów gotowych. Wartość PWT dla zużycia czasu jest pobierana z zasobu lub grupy zasobów z operacji marszruty.
-   **Towar i kategoria** — pozwala używać kont księgowych, które zostały skonfigurowane w grupach towarów dla surowców i wyrobów gotowych. Wartość PWT dla zużycia czasu jest pobierana z kategorii kosztów, które są skojarzone z operacjami marszruty.
-   **Grupy produkcji** — pozwala używać kont księgowych, które zostały ustawione w grupach produkcji zarówno dla materiałów, jak i zużycia czasu. Grupy produkcji są kojarzone ze zwolnionymi produktami i kopiowane do zleceń produkcyjnych podczas tworzenia tych zleceń. Księgowania w zleceniach produkcyjnych będzie następnie przebiegać według grup produkcji skojarzonych ze zleceniem produkcyjnym.

**Uwaga:** Jeśli koszt gotowego towaru obliczany był w standardowy sposób, uwzględniają to także transakcje końcowe. Jeśli istnieje różnica pomiędzy rzeczywistymi kosztami a kosztami obliczonymi w standardowy sposób, jest to księgowane na koncie wykazującym zysk lub stratę.



