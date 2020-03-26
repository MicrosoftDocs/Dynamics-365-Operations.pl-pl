---
title: Omówienie
description: W Dynamics 365 Human Resources obszar roboczy **Urlopy i nieobecności** udostępnia elastyczną strukturę do tworzenia nowych planów urlopów, przepływy pracy do zarządzania wnioskami oraz intuicyjną stronę samoobsługi umożliwiającą pracownikom wnioskowanie o czas wolny.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 493bc3abe82103541125914896252b2eae596b38
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "3091755"
---
# <a name="overview"></a>Omówienie

Program Dynamics 365 Human Resources pomaga oferować pracownikom doskonale warunki urlopowe. Obszar roboczy **Urlopy i nieobecności** udostępnia elastyczną strukturę do tworzenia nowych planów urlopów, przepływy pracy do zarządzania wnioskami oraz intuicyjną stronę samoobsługi umożliwiającą pracownikom wnioskowanie o czas wolny. Funkcje analityczne pomagają organizacji mierzyć i monitorować salda i wykorzystanie urlopów ujętych w planach urlopów.

## <a name="set-up-leave-and-absence"></a>Konfigurowanie obszaru roboczego Urlopy i nieobecności

Zanim będzie można tworzyć plany urlopów dla pracowników, należy wykonać kilka kroków konfiguracyjnych:

- [Konfigurowanie parametrów urlopów i nieobecności](hr-leave-and-absence-parameters.md)
- [Tworzenie kalendarza czasu pracy](hr-leave-and-absence-working-time-calendar.md)
- [Tworzenie przepływu pracy wniosku urlopowego](hr-leave-and-absence-workflow.md)

## <a name="create-and-manage-leave-plans"></a>Tworzenie planów urlopów i zarządzanie nimi

Przed rozpoczęciem tworzenia planów urlopów dla pracowników należy utworzyć typy urlopów i nieobecności. Po utworzeniu planu urlopów można w nim rejestrować pracowników. Można również uruchomić proces naliczania, tworzyć alerty i przeglądać analizy swoich planów.

- [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md)
- [Tworzenie planu urlopów i nieobecności](hr-leave-and-absence-plans.md)
- [Przypisywanie pracowników do planu urlopu](hr-leave-and-absence-enroll.md)
- [Naliczanie do planów urlopów i nieobecności](hr-leave-and-absence-accrue.md)
- [Wyświetlanie analiz urlopów i nieobecności](hr-leave-and-absence-analytics.md)

## <a name="request-time-off-and-manage-requests"></a>Wnioskowanie o czas wolny i zarządzanie wnioskami

W obszarze roboczym **Samoobsługa pracownika etatowego** pracownicy mogą przesyłać wnioski urlopowe, a Ty możesz nimi zarządzać.

- [Żądanie czasu wolnego](hr-employee-self-service-request-time-off.md)
- [Zarządzanie wnioskami urlopowymi](hr-employee-self-service-manage-requests.md)

## <a name="leave-and-absence-preview-features"></a>Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności

W środowisku typu **Piaskownica** można testować nowe funkcje urlopów i nieobecności udostępnione w wersji zapoznawczej. Aby uzyskać informacje na temat włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md). Funkcje w wersji zapoznawczej obejmują:

- **Kalendarz urlopów i nieobecności** — urlop i parametry nieobecności będą przenoszone z parametrów modułu **Human Resources** do nowego ekranu o nazwie **Urlop i nieobecność**. Nowy ekran zawiera nową kartę **Kalendarz**. Ten podgląd umożliwia tylko wgląd w podzestaw parametrów. Nowy ekran można uzyskać, korzystając z karty **Łącza** w obszarze roboczym **urlop i nieobecność**. Do kalendarzy należy:
  - **Kalendarz firmy** — umożliwia wyświetlenie wszystkich żądań wyłączenia czasu pracy pracownika. Osoby z rolą **Human Resources** mogą uzyskać dostęp do tego kalendarza z karty **Łącza** w obszarze roboczym **Urlop i nieobecność**.
  - **Kalendarz zespołu Menedżera** — umożliwia wyświetlenie wszystkich żądań czasu wolnego. Menedżerowie mogą uzyskać dostęp do kalendarza z karty **Mój zespół** w module Samoobsługa pracownika w ramach funkcji **urlop i nieobecność**. 

- **Urlopy i kalendarze - świąteczne nieobecności** — typy urlopów zawierają nową opcję **Urlop świąteczny**, używaną w połączeniu z kalendarzem czasu pracy. Dni określone przez dni wolne i zamknięcia są obecnie wyznaczone jako **Święta** w przypadku generowania dni roboczych. Podczas przetwarzania naliczeń są wprowadzane poprawki - pracownicy przypisani są do kalendarza w celu uwzględnienia świąt przypadających w dniu pracy.

- **Dane dot. urlopu** — nowy ekran umożliwia przeglądanie, kiedy naliczenia zostały przetworzone i usunięte, zarówno przez pracowników, jak i poszczególnych pracowników. Ten nowy ekran można uzyskać, korzystając z karty **Łącza** w obszarze roboczym **Urlop i nieobecność**.

- **Usunięcie danych dot. urlopu** — teraz możesz usunąć rekordy naliczania dla konkretnych planów urlopów. Tę nową opcję można uzyskać, korzystając z karty **Łącza** w obszarze roboczym **Urlop i nieobecność**. W przypadku poszczególnych pracowników ta opcja jest wyświetlana w grupie **Urlop i nieobecność** w profilu pracownika. 

- **Zaokrąglanie danych dot urlopu** — nowe opcje dla **Typu urlopu** umożliwiają zdefiniowanie zaokrąglania, powiększonej o precyzję dziesiętną zaokrąglenia w procesie naliczania. Podczas przetwarzania naliczeń w rekordach naliczania są stosowane zaokrąglenie i precyzja. 

- **Konfigurowanie wielu typów urlopu dla jednego planu** — nowa kolumna w harmonogramie wystawiania urlopów dla typów urlopów umożliwia zdefiniowanie wielu typów urlopów w przypadku urlopu i nieobecności z różnymi harmonogramami naliczania. Pole poprzedniego **Typu urlopu** jest usunięte. Przy zarejestrowaniu pracownika, salda dla typów urlopu są teraz wyświetlane w tabeli, a nie w górnej części ekranu.

  > [!IMPORTANT]
  > Po włączeniu tej funkcji nie można jej wyłączyć.

- **Użycie ekwiwalentu pełnego etatu pracownika etatowego (FTE) w celu naliczenia** — nowa kolumna w harmonogramie naliczania urlopu umożliwia używanie pełnego ekwiwalentu FTE do naliczania. Podczas przetwarzania naliczeń aplikacja używa podstawowego stanowiska pracownika oraz pełnego etatu zdefiniowanego w celu określenia proporcjonalnej kwoty naliczania.

  > [!NOTE]
  > Ta funkcja jest dostępna tylko po włączeniu opcji **Skonfiguruj wiele typów urlopu dla jednego planu urlopu**. 
