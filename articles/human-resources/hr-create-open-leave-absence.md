---
title: Tworzenie otwartej nieobecności
description: W tym artykule opisano sposób tworzenia otwartego-zakończonego urlopu w Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 08231d4139209387c3c76923fafdd2061fceb280
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805345"
---
# <a name="create-an-open-ended-leave-of-absence"></a>Tworzenie otwartej nieobecności

> [!IMPORTANT]
> Funkcjonalność opisana w tym artykule będzie dostępna w infrastrukturze Finance jako część przyszłej wersji po Microsoft Dynamics 365 Finance w wersji 10.0.31.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Możesz przesyłać wnioski o urlop na czas nieokreślony i wyświetlać stan swoich wniosków o urlop w Dynamics 365 Human Resources.

## <a name="prerequisites"></a>Wymagania wstępne

1. W obszarze **Zarządzanie funkcjami** upewnij się, że funkcja **Otwarte zakończone urlopy** jest włączona.

    > [!IMPORTANT]
    > Tej funkcji nie można wyłączyć po jej włączeniu.

2. Umożliwia tworzenie typu urlopu.
3. Wprowadź szczegóły, takie jak typ urlopu, opis i identyfikator przepływu pracy.
4. W polu **Typ wniosku** wybierz pozycję **Nieobecność**.
5. W sekcji ze szczegółami dla kart otwartych ustaw opcję **Otwarte** na **Tak**.
6. Ustaw opcję **Powiadomienie o powrocie do pracy** na **Tak** lub **Nie**.
7. W przypadku wniosków urlopowych może być opcjonalnie wymagane powiadomienie dotyczące powrotu do pracy.

> [!NOTE]
> Po włączeniu tej funkcji zostanie włączona funkcja **Wymagany załącznik**.

## <a name="request-an-open-ended-leave-of-absence"></a>Poproś o urlop na czas nieokreślony

1. W obszarze roboczym **Samoobsługa pracownicza** na kafelku **Czas pozabilansowy** wybierz opcję **Więcej (...)**.
2. Aby przesłać wniosek o urlop, wybierz pozycję **Złóż wniosek o urlop**.
3. Wypełnij pola **Typ urlopu**, **Data rozpoczęcia**. W polu **Data/godzina zakończenia** wprowadź wstępną datę końcową.
4. Jeśli musisz przesłać dokumentację uzupełniającą, w obszarze **Załączniki** wybierz **Prześlij**.
5. Jeśli wszystko jest gotowe do przesłania prośby, wybierz opcję **Prześlij**. W przeciwnym razie wybierz opcję **Zapisz wersję roboczą**.
6. Aby zaktualizować wniosek o urlop na czas nieokreślony, wybierz wniosek, wprowadź datę końcową w polu **Data końcowa**, ustaw opcję **Potwierdź datę końcową** na **Tak** i prześlij dokumentację .
7. Jeśli opcja **Powiadomienie o powrocie do pracy** jest ustawiona na **Tak**, wybierz opcję **Prześlij**, a następnie zaznacz pole wyboru, aby potwierdzić, że przesłano prawidłowe powiadomienie o powrocie do pracy.
8. Po wprowadzeniu wszystkich szczegółów wybierz pozycję **Prześlij**.
