---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (31 stycznia 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 01/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-01-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8e8c11e460a4678efea81f8d3d1eec96b673d329
ms.sourcegitcommit: 53174ed4e7cc4e1ba07cdfc39207e7296ef87c1f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/07/2020
ms.locfileid: "4690059"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-31-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (31 stycznia 2019 r.)

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.

**Kompilacja 8.1.2128**

## <a name="core-hr-changes"></a>Zmiany w Core HR

### <a name="time-off-taken-on-leave-people-card-doesnt-consider-leave-plan-dates"></a>Czas wolny wzięty na karcie urlopów osób nie bierze pod uwagę dat planu urlopów
Dla planów urlopów, które nie działają w roku kalendarzowym, karta **Zajęte** pokazuje teraz czas wolny wzięty w roku urlopowym zdefiniowanym w planie. Na przykład jeśli rok urlopowy w organizacji jest od 1 czerwca do 30 maja, a pracownik wziął trzy dni urlopu w grudniu, karta **Zajęte** na dzień 15 stycznia będzie pokazywała 3 dni. 

### <a name="accrual-amounts-not-matching-tier-date-basis"></a>Naliczane kwoty nie pasują do podstawy daty warstwy
Nowe opcje dodano do urlopów i nieobecności (parametry **Zasoby ludzkie**) umożliwiające klientom ustalenie, kiedy obowiązują miesiące daty rozpoczęcia pracy pracowników. W niektórych organizacjach ta data jest ostatnim dniem miesiąca, ale w innych może być to początek następnego miesiąca. Na przykład jedna organizacja może udzielać czasu wolnego 31 grudnia, a inna może udzielać czasu wolnego od 1 stycznia. Ta opcja pozwoli wybrać podczas, kiedy ma nastąpić to udzielenie. 

### <a name="worker-hire-actions-are-stuck-in-workflow-complete-state"></a>Działania związane z zatrudnieniem pracownika utknęły w stanie „Przepływ pracy zakończony”
Wprowadzono zmiany, aby rozwiązać problem polegający na tym, że niewielka liczba przepływów pracy kończyła się stanem „Przepływ pracy zakończony”. Nowe przepływy pracy powinny teraz przechodzić do stanu „Ukończony” po zakończeniu przepływu pracy. Wszystkie przepływy pracy w stanie ukończenia przepływu pracy zostaną przełączone w stan błędu, który pozwoli na ich zaktualizowanie lub usunięcie, w zależności od potrzeb. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]