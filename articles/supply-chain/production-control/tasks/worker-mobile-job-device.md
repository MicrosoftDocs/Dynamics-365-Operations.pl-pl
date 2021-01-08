---
title: Konfigurowanie pracownika za pomocą urządzenia przenośnego zadania
description: Ten temat objaśnia, jak przypisać poprawne role do konta użytkownika pracownika, a następnie włączyć pracownikowi możliwość rejestrowania się na produkcji.
author: ShylaThompson
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ada42a98a8a87e377f939d063b17f9904f6b3408
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435389"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a>Konfigurowanie pracownika za pomocą urządzenia przenośnego zadania

[!include [banner](../../includes/banner.md)]

Ten temat objaśnia, jak przypisać poprawne role do konta użytkownika pracownika, a następnie włączyć pracownikowi możliwość rejestrowania się na produkcji.

## <a name="verify-that-a-worker-is-assigned-a-certain-role"></a>Sprawdzanie, czy pracownik ma przypisaną odpowiednią rolę

W tym przykładzie należy sprawdzić, czy użytkownik „SHANNON” ma przypisaną rolę operatora maszyny przed skonfigurowaniem konta pracownika.

1. Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Użytkownicy > Użytkownicy**.
2. Wyszukaj użytkownika w szybkim filtrze. W tym przykładzie wpisz `shannon`.
3. Wybierz łącze w kolumnie **Identyfikator użytkownika** wyświetlonego konta użytkownika.
4. W drzewie **Role użytkownika** wybierz **Role > Operator maszyny**.
5. Zamknij strony **szczegóły użytkownika** i **użytkownicy**, aby powrócić do strony głównej.

## <a name="configure-worker-account"></a>Konfigurowanie konta pracownika
1. Przejdź do **okienka nawigacji > Moduły > Zasoby ludzkie > Pracownicy > Pracownicy**.
2. Wyszukaj użytkownika w szybkim filtrze. W tym przykładzie wpisz `shannon`.
3. Wybierz łącze w kolumnie **Nazwa** wyświetlonego konta użytkownika.
4. Wybierz kartę **Rejestracja czasu**.
5. Wybierz **Aktywowanie na terminalach rejestracji**.
6. Wpisz lub wybierz wartości w następujących polach:  

    - **Grupa obliczania**  
    - **Domyślna grupa obliczania**  
    - **Grupa zatwierdzania**  
    - **Profil standardowy**  
    - **Grupa profilu**  

7. Kliknij przycisk **OK**.
8. Wybierz **Edytuj**, aby wprowadzić numer karty identyfikacyjnej nowego pracownika odpowiedzialnego za rejestrację czasu. Wprowadź wartość w polu **Identyfikator karty identyfikacyjnej**.
9. Wybierz opcję **Zapisz**.
10. Zamknij strony **Szczegóły pracownika** i **Pracownicy**.

## <a name="assign-worker-to-device-group"></a>Przypisywanie pracownika do grupy urządzeń
1. Wybierz kolejno opcje **Kontrola produkcji > Ustawienia > Wykonywanie produkcji > Konfiguruj kartę zadań dla urządzeń**.
2. Wybierz opcję **Dodaj**.
3. Na liście zaznacz żądanego pracownika. W tym przykładzie wybierz **SHANNON**.
4. Kliknij przycisk **OK**.
5. Wybierz opcję **Edycja**.
6. W polu **Jednostka produkcyjna** można ustawić domyślny filtr dla pracownika. Daje to pewność, że gdy pracownik loguje się do urządzenia, wyświetlane są tylko zadania produkcyjne dla wybranej jednostki produkcyjnej. Wprowadź odpowiednią wartość.
7. Zamknij stronę.

