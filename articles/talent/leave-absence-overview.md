---
title: "Omówienie zarządzania urlopami i nieobecnościami"
description: "Ten temat zawiera omówienie modułu Zarządzanie urlopami i nieobecnościami. Moduł ten oferuje elastyczną architekturę definiowania procesu zarządzania nieobecnościami. Można tworzyć plany urlopów i nieobecności w celu określenia, jak pracownikom jest naliczany lub przyznawany czas wolny."
author: ryansandness
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3fd3842f2e69e8f5d5e269a61ca7f3ec0ff471c0
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="leave-and-absence-management-overview"></a>Omówienie zarządzania urlopami i nieobecnościami

Moduł **Zarządzanie urlopami i nieobecnościami** oferuje elastyczną architekturę definiowania procesu zarządzania nieobecnościami. Można tworzyć plany urlopów i nieobecności w celu określenia, jak pracownikom jest naliczany lub przyznawany czas wolny. Gdy pracownicy zostaną zarejestrowani w planie, mogą przesyłać wnioski o czas wolny do zatwierdzenia przez menedżerów. Funkcja śledzenia urlopów umożliwia zarówno menedżerom pierwszego szczebla, jak i menedżerom kadr (HR) sprawdzanie, kto korzysta z czasu wolnego i ile ma jeszcze czasu wolnego.  

Moduł Zarządzanie urlopami i nieobecnościami udostępnia następujące funkcje: 

- **Definiowanie typów urlopów i nieobecności.**

    Typy urlopów określają różne rodzaje nieobecności, które pracownicy mogą zgłaszać. Ponieważ te typy są definiowane przez użytkowników, mogą być dostosowane do organizacji. Popularne typy urlopów to m.in. płatny urlop (PTO), urlop, urlop z powodu krótkotrwałej niezdolności do pracy, urlop z powodu obowiązków sędziego przysięgłego (specyficzny dla Stanów Zjednoczonych) i urlop okolicznościowy. 

- **Definiowanie warstwowych planów urlopów i nieobecności uwzględniających specyfikę firmy.**

    Plany urlopów i nieobecności można zdefiniować tak, aby naliczanie odbywało się z określoną częstotliwością, na przykład raz w roku, co miesiąc czy dwa razy w miesiącu. Plany można również zdefiniować jako przydziały, gdzie jedno naliczanie odbywa się w określonym dniu. 

    Plany urlopów często zawierają warstwy, w których pewne grupy pracowników otrzymują dodatkowe świadczenia zależne od ilości czasu przynależności do organizacji. Te warstwy są definiowane przez użytkowników i umożliwiają automatyczne rejestrowanie na godziny dodatkowych świadczeń w oparciu o ustalone kryteria dat. W planach urlopów można również skonfigurować wymuszanie maksymalnej ilości przeniesienia lub minimalnego salda, tak aby zapobiec wykorzystywaniu przez pracowników większej liczby godzin świadczeń, niż zostało naliczone. 

    Typowe plany urlopów obejmują plany warstwowe, które przyznają 80 godzin płatnego urlopu nowym pracownikom, ale 120 godzin po upływie 60 miesięcy pracy. Dodatkowe plany mogą przyznawać urlopy na żądanie lub świadczenia zależne od stanowiska, na przykład urlopy tylko dla członków wyższej kadry kierowniczej.

- **Rejestrowanie pracowników w planach urlopów i zwolnień indywidualnie lub w ramach przypisania grupowego opartego na kryteriach stanowiska.**

    Można użyć kilku filtrów związanych ze stanowiskami, aby przypisać grupę pracowników do planu urlopów. Menedżerowie ds. HR mogą wyświetlać pracownika, aby zobaczyć, w jakich planach urlopów i nieobecności jest zarejestrowany. Alternatywie menedżerowie ds. HR mogą wyświetlać wszystkie plany i odnośne rejestracje pracowników.

- **Zawieszanie planów urlopów i nieobecności.**

    Plany urlopów i nieobecności można zawieszać, aby je zdezaktywować i zapobiec dodatkowym naliczeniom. Naliczenia zostają zawieszone dla pracowników, gdy kończy się ich zatrudnienie.  

- **Dostosowywanie uprawnień i przydziałów.**

    Pracownik może zostać zarejestrowany w wyższej warstwie planu przy użyciu daty specyficznej dla pracownika, co zastąpi domyślną ofertę planu dla pracownika. Pracownicy mogą otrzymywać ręczne korekty salda urlopów i nieobecności w momencie rejestrowania w planie lub też dział kadr może wprowadzać ręczne korekty w dowolnym momencie. 

- **Stosowanie przepływu pracy do wniosków o czas wolny.**

     Przepływ pracy może być dostosowywany i stosowany do wniosków o czas wolny zgodnie z wymaganiami organizacji.  

- **Śledzenie salda nieobecności pracowników.**

    Pracownicy, ich menedżerowie i dział kadr mogą wyświetlać salda urlopów i nieobecności. Dział kadr może używać interaktywnych raportów do śledzenia rejestracji w planach i sald czasu wolnego według typów. 

- **Przesyłanie wniosków o czas wolny.**

    Pracownicy mogą przesyłać wnioski o czas wolny względem dostępnej dla siebie liczby godzin. Wnioski mogą być prostymi wnioskami na jeden dzień lub obejmować wiele dni, z kilkoma typami urlopów i nieobecności. Jeśli funkcja przepływu pracy nie jest włączona, wnioski są automatycznie zatwierdzane. Gdy funkcja przepływu pracy jest włączona, zatwierdzenie może odbywać się automatycznie lub wymagać podpisania, zależnie od konfiguracji przepływu pracy.

