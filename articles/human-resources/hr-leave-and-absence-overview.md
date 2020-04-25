---
title: Omówienie
description: W Dynamics 365 Human Resources obszar roboczy Urlopy i nieobecności udostępnia elastyczną strukturę do tworzenia nowych planów urlopów, przepływy pracy do zarządzania wnioskami oraz intuicyjną stronę samoobsługi umożliwiającą pracownikom wnioskowanie o czas wolny.
author: andreabichsel
manager: AnnBe
ms.date: 04/03/2020
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
ms.openlocfilehash: 5f7ba32b31a67d81ee5be568b0e64842f343f96b
ms.sourcegitcommit: 9940ca772807d3c4e1ff3bf47f45b7251c4469ac
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/04/2020
ms.locfileid: "3226237"
---
# <a name="overview"></a>Omówienie

Program Dynamics 365 Human Resources pomaga oferować pracownikom doskonale warunki urlopowe. Obszar roboczy **Urlopy i nieobecności** udostępnia elastyczną strukturę do tworzenia nowych planów urlopów, przepływy pracy do zarządzania wnioskami oraz intuicyjną stronę samoobsługi umożliwiającą pracownikom wnioskowanie o czas wolny. Funkcje analityczne pomagają organizacji mierzyć i monitorować salda i wykorzystanie urlopów ujętych w planach urlopów.

## <a name="set-up-leave-and-absence"></a>Konfigurowanie obszaru roboczego Urlopy i nieobecności

Zanim utworzy się plany urlopów dla pracowników, należy wykonać kilka kroków konfiguracyjnych:

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

- [Złóż wniosek o czas wolny](hr-employee-self-service-request-time-off.md)
- [Zarządzanie wnioskami o urlop i nieobecność](hr-employee-self-service-manage-requests.md)

## <a name="leave-and-absence-known-issues"></a>Problemy z urlopem i nieobecnością

### <a name="rounding-precision"></a>Dokładność zaokrąglania

Nie można ustawić **Dokładność zaokrąglania** podczas ustawiania **Typ zaokrąglania**. **Dokładność zaokrąglania** można ustawiać tylko przy użyciu jednostki **Typy urlopów i nieobecności**. 

1. Z **Typy urlopów i nieobecności** wybierz **Otwórz w programie Excel**, aby otworzyć jednostkę **Typy urlopów i nieobecności**.

2. Po otwarciu i włączeniu pliku wybierz opcję **Projekt**.

3. W tabeli **Typy urlopów i nieobecności** wybierz opcję ołówek, aby edytować.

4. Wybierz **RoundingPrecision** i **RoundingType**, a następnie wybierz **Dodaj**, aby dodać do listy pól.

5. Zaznacz element **Aktualizuj** i kliknij przycisk **Gotowe**.

6. Wprowadź lub wybierz **Typ zaokrąglania** dla każdego typu urlopu, jeśli nie zostały one jeszcze ustawione. 

7. Umożliwia wprowadzenie **Dokładności zaokrąglenia** dla odpowiednich typów.

8. Wybierz opcję **Publikuj**, aby wprowadzić zmiany również do Human Resources.

## <a name="leave-and-absence-preview-features"></a>Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności

W środowisku typu **Piaskownica** można testować nowe funkcje urlopów i nieobecności udostępnione w wersji zapoznawczej. Aby uzyskać informacje na temat włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md). Funkcje w wersji zapoznawczej obejmują:

- **Zawieszenie urlopu** — istnieje możliwość zawieszenia urlopu i nieobecności w Human Resources dla pracownika etatowego. Zawieszenie urlopu powoduje zatrzymanie naliczania dla wybranych typów urlopów. Jeśli zawieszenie następuje po procesach naliczania, wstrzymanie urlopu powoduje utworzenie skorygowanej korekty salda urlopu pracownika. 

- **Przenieś reguły do przodu** — można określić typ urlopu przeniesienia do przodu dla sald przeniesionych na następny okres, gdzie są przenoszone korekty do przodu. Jeśli na przykład pracownik przeniósł 10 dni do przodu, można wybrać inny typ urlopu dla tych 10 dni. 