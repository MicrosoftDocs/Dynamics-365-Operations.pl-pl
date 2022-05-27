---
title: Zarejestrowanie pracownika w systemie stałych wynagrodzeń
description: Menedżer ds. wynagrodzenia i świadczeń może przypisywać pracowników do planów stałych wynagrodzeń w celu zarządzania ich wynagrodzeniami podstawowymi.
author: twheeloc
ms.date: 08/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup, HcmCompensationWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d611f2631a59fbe1e131e82ca9937a5adaaf2ebd
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688749"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a>Zarejestrowanie pracownika w systemie stałych wynagrodzeń


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Menedżer ds. wynagrodzenia i świadczeń może przypisywać pracowników do planów stałych wynagrodzeń w celu zarządzania ich wynagrodzeniami podstawowymi. Ta procedura zakłada, że plan stałych wynagrodzeń został utworzony i jest aktywny oraz skonfigurowano w nim reguły uprawnienia. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Aby rozpocząć procedurę, wybierz kolejno opcje **Zasoby ludzkie** > **Pracownicy** > **Pracownicy etatowi** > **Wynagrodzenie** > **Plan stałych wynagrodzeń**.

1. Kliknij przycisk **Nowy**.
2. W polu **Akcja** wybierz akcję związaną ze stałym wynagrodzeniem typu **Zatrudnienie/ponowne zatrudnienie**, aby opisać zmianę wynagrodzenia pracownika etatowego.
3. Na liście kliknij łącze w wybranym wierszu.
4. W polu **Stanowisko** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście kliknij łącze w wybranym wierszu.
    * Poziom wyświetlany z poziomu pola skróconej karty **Wynagrodzenia** > **Poziom** dla **Zadania** przypisanego do **Stanowiska**. Aby wynagrodzenie można było przypisać do pracownika, poziom musi zostać ustawiony w zadaniu.  
6. W polu **Plan** wybierz plan stałych wynagrodzeń dla pracownika. Wyszukiwanie **planu** zostanie wyfiltrowane w celu wyświetlenia tylko planów, do których pracownik jest uprawniony zgodnie z **regułami uprawnień**.
7. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wartości pól **Data obowiązywania** i **Data wygaśnięcia** dla wynagrodzenia domyślnie pochodzą z daty rozpoczęcia i zakończenia przypisania stanowiska pracownika. W razie potrzeby można zmienić te daty.  
    * Jeśli plan stałych wynagrodzeń jest planem typu Krok, zaznacz krok zawierający stawkę płacy odpowiednią dla pracownika. Jeśli plan stałych wynagrodzeń jest planem typu Pasmo lub Kategoria, wprowadź stawkę płacy pracownika. Stawka płacy będzie weryfikowana względem ustawień tolerancji dla planu oraz minimalnego i maksymalnego punktu odniesienia w poziomie wynagrodzeń dla zadania.  
8. Kliknij przycisk **OK**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
