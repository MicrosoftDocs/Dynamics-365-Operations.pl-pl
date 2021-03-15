---
title: Zarejestrowanie pracownika w systemie stałych wynagrodzeń
description: Menedżer ds. wynagrodzenia i świadczeń może przypisywać pracowników do planów stałych wynagrodzeń w celu zarządzania ich wynagrodzeniami podstawowymi.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bc8373a4a39a1a212ab445b2b300fbddfe0e4a39
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113863"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a>Zarejestrowanie pracownika w systemie stałych wynagrodzeń

Menedżer ds. wynagrodzenia i świadczeń może przypisywać pracowników do planów stałych wynagrodzeń w celu zarządzania ich wynagrodzeniami podstawowymi. Ta procedura zakłada, że plan stałych wynagrodzeń został utworzony i jest aktywny oraz skonfigurowano w nim reguły uprawnienia. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Aby rozpocząć procedurę, wybierz kolejno opcje Zasoby ludzkie > Pracownicy > Pracownicy > Wynagrodzenie > Plan stałych wynagrodzeń.

1. Kliknij przycisk Nowy.
2. W polu Akcja wybierz akcję związaną ze stałym wynagrodzeniem typu Zatrudnienie/ponowne zatrudnienie, aby opisać zmianę wynagrodzenia pracownika.
3. Na liście kliknij łącze w wybranym wierszu.
4. W polu Stanowisko kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście kliknij łącze w wybranym wierszu.
    * Poziom wyświetlany z poziomu wynagrodzeń dla zadania na tym stanowisku. Aby wynagrodzenie można było przypisać do pracownika, poziom musi zostać ustawiony w zadaniu.  
6. W polu Plan wybierz plan stałych wynagrodzeń dla pracownika. Wyszukiwanie planu zostanie wyfiltrowane w celu wyświetlenia tylko planów, do których pracownik jest uprawniony zgodnie z regułami uprawnień.
7. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wartości pól Data obowiązywania i Data wygaśnięcia dla wynagrodzenia domyślnie pochodzą z daty rozpoczęcia i zakończenia przypisania stanowiska pracownika. W razie potrzeby można zmienić te daty.  
    * Jeśli plan stałych wynagrodzeń jest planem typu Krok, zaznacz krok zawierający stawkę płacy odpowiednią dla pracownika. Jeśli plan stałych wynagrodzeń jest planem typu Pasmo lub Kategoria, wprowadź stawkę płacy pracownika. Stawka płacy będzie weryfikowana względem ustawień tolerancji dla planu oraz minimalnego i maksymalnego punktu odniesienia w poziomie wynagrodzeń dla zadania.  
8. Kliknij przycisk OK.



[!INCLUDE[footer-include](../includes/footer-banner.md)]