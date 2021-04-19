---
title: Ustawienia preferowanych konserwatorów
description: W tym temacie wyjaśniono, jak konfigurować preferowanych konserwatorów w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkerPreferred
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5b044e4616555559be51b0846327b1d55bfe47b3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822546"
---
# <a name="set-up-preferred-maintenance-workers"></a>Ustawienia preferowanych konserwatorów

[!include [banner](../../includes/banner.md)]

 

Podczas planowania zlecenia pracy, użytkownik może ustawić preferencję, na której konserwatorzy lub grupy konserwatorów są przydzielane do wykonywania zleceń pracy. Korzystanie z tej funkcji jest opcjonalne, ale może pomóc w wyborze najbardziej kwalifikowanego pracownika obsługi do wykonania zadania na podstawie umiejętności i kwalifikacji pracownika. Zaplanowane są tylko pracownicy obsługi, którzy są dostępni w czasie planowania. Jeśli preferowana konfiguracja pracownika obsługi jest zgodna z zleceniem w trakcie planowania, ale pracownik obsługi jest przydzielany do innych zadań, zlecenie pracy będzie zaplanowane na inną, dostępną dla konserwatora.

Aby można było skonfigurować preferowanych konserwatorów, należy najpierw skonfigurować konserwatorów i grupy konserwatorów. Aby uzyskać informacje na temat konfiguracji konserwatorów i grup konserwatorów, zobacz temat [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md).

## <a name="set-up-preferred-workers"></a>Ustawienia preferowanych pracowników

Preferowany pracownik konserwacji lub grupa konserwatorów może być powiązana z jednym lub więcej z następujących:

- handel  
- wariantem typu zadania konserwacji  
- typem zadania konserwacji  
- kategorią typu zadania konserwacji  
- aktywa  
- typem składnika majątku  

Im więcej opcji zostanie wprowadzonych dla tego samego rekordu, tym dokładniejsze będą ustawienia.

1. Kliknij **Zarządzanie składnikami majątku** > **Ustawienia** > **Pracownicy** > **Preferowani konserwatorzy**.

2. Naciśnij przycisk **Nowy**, aby utworzyć nowy rekord.

3. Aby rozpocząć, Utwórz „domyślnego” konserwatora lub grupę konserwatorów. Oznacza to , że można wybierać tylko w polu **Preferowana grupa konserwatorów** lub w polu **preferowany konserwator**. Na poniższym zrzucie ekranu widać przykład w pierwszym rekordzie, w którym "żądania" są wybrane jako **Preferowana grupa konserwatorów**.

    [!NOTE] Ta domyślna konfiguracja będzie używana podczas planowania zleceń pracy, jeśli żadna inna określona kombinacja nie pasuje do zawartości zlecenia pracy.

4. Powtórz krok 2, aby utworzyć nowy rekord. Dokonaj wymaganych wyborów w zależności od poziomu szczegółowości dla preferowanego pracownika lub grupy pracowników. 

    *Przykład:* na poniższym zrzucie ekranu, w szóstym rekordzie, konserwator Shawn Richardson jest wybrany jako pracownik preferowany. Zostanie on automatycznie wybrany podczas planowania zlecenia pracy zawierającego środek trwały „CH-BP1-03-02” i typ zadania konserwacji „Ocena instrumentu”, jeśli jest on dostępny w zaplanowanym czasie.

    [!NOTE] Jeśli podczas planowania zlecenia pracy wybrano preferowanego konserwatora, Zarządzanie składnikami majątku przechodzi przez wszystkie rekordy **perferowanych konserwatorów**, aby sprawdzić, czy są dostępne w pierwszej kolejności najbardziej specyficzne dane. Jeśli nie zostanie znalezione dopasowanie, zostanie użyty rekord domyślny z wyborem w polu **preferowana grupa konserwatorów** lub w polu **preferowany konserwator**.

![Rysunek 1](media/02-work-order-scheduling.png)

Można również skonfigurować *odpowiedzialnych* konserwatorów, którzy mogą być wybrani w momencie utworzenia zlecenia konserwacji lub zlecenia pracy. Można edytowac wszystkie wybory w **Wszystkie zlecenia pracy** i **Wszystkie żądania konserwacji** w razie potrzeby. Aby uzyskać więcej informacji należy zapoznać się z [Odpowiedzialni konserwatorzy](../setup-for-maintenance-requests/responsible-workers.md).

Podczas planowania zlecenia pracy różne wyniki są obliczane w celu określenia, którzy pracownicy powinni spełniać zadania związane z danym zleceniem (te okresy są ustawiane w **Parametry zarządzania składnikami majątku** > **Planowanie zlecenia pracy** łącze). Jeśli w przypadku dwóch lub więcej preferowanych pracowników konserwacji lub pracowników odpowiedzialnych za konserwacje uzyskuje się ten sam wynik podczas planowania zleceń, jeden pracownik jest wybierany losowo. W przeciwnym razie jest on zawsze pracownikiem o najwyższyej ocenie, który jest przydzielony do wykonania zlecenia pracy.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]