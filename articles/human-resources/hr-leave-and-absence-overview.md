---
title: Omówienie
description: W Dynamics 365 Human Resources obszar roboczy Urlopy i nieobecności udostępnia elastyczną strukturę do tworzenia nowych planów urlopów, przepływy pracy do zarządzania wnioskami oraz intuicyjną stronę samoobsługi umożliwiającą pracownikom wnioskowanie o czas wolny.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ec72d2d741f7f8428a7daa97bb982e9fc00b8c3f
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428974"
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

W środowisku typu **Piaskownica** można testować nowe funkcje urlopów i nieobecności udostępnione w wersji zapoznawczej. Aby uzyskać informacje na temat włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md). 

[!include [banner](includes/preview-feature.md)]

Funkcje w wersji zapoznawczej obejmują:

- **Pozostaw naliczenie według firmy lub planu** — można uruchomić proces naliczania dla wszystkich firm lub dla jednej firmy. Można również uruchomić proces naliczania dla określonego planu urlopu i nieobecności dla danej firmy. 

- **Kupuj urlop** — możesz włączyć i utworzyć zasady kupna urlopu dla pracowników, aby wysyłać wnioski zakupu. Pracownicy mogą przesyłać wnioski zakupu i mieć salda automatycznie aktualizowane w celu odzwierciedlenia tego wniosku.  

- **Dodaj załączniki do zatwierdzonych wniosków urlopu** — możesz dodać załącznik do wniosku urlopowego, który już został zatwierdzony. 

