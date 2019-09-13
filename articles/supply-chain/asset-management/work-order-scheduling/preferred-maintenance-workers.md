---
title: Ustawienia preferowanych konserwatorów
description: W tym temacie wyjaśniono, jak konfigurować preferowanych konserwatorów w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f26be81e7057d0cea1473d81452216251633ad9
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887418"
---
# <a name="preferred-maintenance-workers"></a>Preferowani konserwatorzy

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Użytkownik może ustawić preferencję, na której pracownicy konserwacji są przydzielani do wykonywania zleceń pracy podczas planowania zlecenia pracy. Korzystanie z tej funkcji jest opcjonalne, ale może pomóc w wyborze najbardziej kwalifikowanego pracownika obsługi do wykonania zadania na podstawie umiejętności i kwalifikacji pracownika. Dlatego podczas planowania zlecenia produkcyjnego ustawienia w **preferowanych konserwatorach** służą do ustalania, czy dla zlecenia pracy ma być zaplanowany określony pracownik obsługi czy grupa pracowników. Zaplanowane są tylko pracownicy obsługi, którzy są dostępni w czasie planowania. Jeśli preferowana konfiguracja pracownika obsługi jest zgodna z zleceniem w trakcie planowania, ale pracownik obsługi jest przydzielany do innych zadań, zlecenie produkcyjne będzie zaplanowane na inną, dostępną dla pracownika obsługi.

Aby można było skonfigurować preferowanych konserwatorów, należy skonfigurować konserwatorów oraz grupy konserwatorów, które powinny być dostępne do wybrania. Aby uzyskać informacje na temat konfiguracji konserwatorów i grup pracowników, zobacz temat [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md).

## <a name="set-up-preferred-workers"></a>Ustawienia preferowanych pracowników

Preferowany pracownik konserwacji lub grupa pracowników może być powiązana z określonym

- handel  
- wariantem typu zadania konserwacji  
- typem zadania konserwacji  
- kategorią typu zadania konserwacji  
- aktywa  
- typem składnika majątku  

lub kombinacją tych opcji. Im więcej opcji zostanie wprowadzonych dla tego samego rekordu, tym dokładniejsze będą ustawienia.

1. Kliknij **Zarządzanie składnikami majątku** > **Ustawienia** > **Pracownicy** > **Preferowani konserwatorzy**.

2. Naciśnij przycisk **Nowy**, aby utworzyć nowy rekord.

3. Należy rozpocząć od utworzenia konfiguracji „domyślna” konserwatora lub grupy konserwatorów dla obsługi, która nie ma wybranych opcji w polach podanych na liście punktowanej powyżej. Oznacza to , że można wybierać tylko w polu **Preferowana grupa konserwatorów** lub w polu **preferowany konserwator**. Na poniższym rysunku widać przykład w pierwszym rekordzie, w którym "żądania" są wybrane jako preferowana grupa konserwatorów.

>[!NOTE]
>Ta domyślna konfiguracja będzie używana podczas planowania zleceń pracy, jeśli żadna inna określona kombinacja nie pasuje do zawartości zlecenia pracy podczas planowania zlecenia.

4. Powtórz krok 2, aby utworzyć nowy rekord. Dokonaj wymaganych wyborów w zależności od poziomu szczegółowości dla preferowanego pracownika lub grupy pracowników. *Przykład:* na poniższym rysunku, w szóstym rekordzie, pracownik obsługi technicznej Shawn Richardson jest wybrany jako pracownik preferowany. Zostanie on automatycznie wybrany podczas planowania zlecenia pracy zawierającego środek trwały „CH-BP1-03-02” i typ zadania konserwacji „Ocena instrumentu”, jeśli jest on dostępny w zaplanowanym czasie.

>[!NOTE]
>Jeśli podczas planowania zlecenia pracy wybrano preferowanego konserwatora, Zarządzanie składnikami majątku przechodzi przez wszystkie rekordy **perferowanych konserwatorów**, aby sprawdzić, czy są dostępne w pierwszej kolejności najbardziej specyficzne dane. Jeśli nie zostanie znalezione dopasowanie, zostanie użyty rekord domyślny z wyborem w polu **preferowana grupa konserwatorów** lub w polu **preferowany konserwator**.


![Rysunek 1](media/02-work-order-scheduling.png)

Można również skonfigurować odpowiedzialnych pracowników obsługi, którzy mogą być wybrani w momencie utworzenia zlecenia serwisowego lub zlecenia pracy. W przypadku **Wszystkie zlecenia pracy** i **Wszystkie żądania konserwacji**, w razie potrzeby można edytować zaznaczenie. Aby uzyskać więcej informacji należy zapoznać się z [Odpowiedzialni konserwatorzy](../setup-for-maintenance-requests/responsible-workers.md).

Podczas planowania zlecenia pracy różne wyniki są obliczane w celu określenia, którzy pracownicy powinni spełniać zadania związane z danym zleceniem (te okresy są ustawiane w **Parametry zarządzania składnikami majątku** > **Planowanie zlecenia pracy** łącze). Jeśli w przypadku dwóch lub więcej preferowanych pracowników konserwacji lub pracowników odpowiedzialnych za konserwacje uzyskuje się ten sam wynik podczas planowania zleceń, jeden pracownik jest wybierany losowo. W przeciwnym razie jest on zawsze pracownikiem o najwyższyej ocenie, który jest przydzielony do wykonania zlecenia pracy.

