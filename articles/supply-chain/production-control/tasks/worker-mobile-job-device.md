---
title: Konfigurowanie pracownika za pomocą urządzenia przenośnego zadania
description: W tej procedurze pokazano, jak przypisać poprawne role do konta użytkownika pracownika, a następnie włączyć pracownikowi możliwość rejestrowania się na produkcji.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1bb4d806810660e55ef13a9ff21c07e0ce194496
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "327396"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a>Konfigurowanie pracownika za pomocą urządzenia przenośnego zadania

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano, jak przypisać poprawne role do konta użytkownika pracownika, a następnie włączyć pracownikowi możliwość rejestrowania się na produkcji.


## <a name="assign-roles-to-user-account"></a>Przypisywanie ról do konta użytkownika
1. Wybierz kolejno opcje Administrowanie systemem > Użytkownicy > Użytkownicy.
2. Za pomocą szybkiego filtru wyfiltruj imię i nazwisko pracownika, którego konto użytkownika jest skojarzone z rolą operatora maszyny. W przykładowych danych jest to Shannon.
3. Zaznacz rekord konta użytkownika.
4. Na liście w zaznaczonym wierszu kliknij łącze „Nazwa”, aby wyświetlić szczegółowe informacje o koncie użytkownika.
5. W drzewie zaznacz element „Role\Operator maszyny”.
6. Zamknij stronę szczegółów konta użytkownika.
7. Zamknij stronę.

## <a name="configure-worker-account"></a>Konfigurowanie konta pracownika
1. Wybierz kolejno opcje Zasoby ludzkie > Pracownicy > Pracownicy.
2. Za pomocą szybkiego filtru wyfiltruj imię i nazwisko pracownika, którego konto użytkownika jest skojarzone z rolą operatora maszyny. W przykładowych danych jest to Shannon.
3. Zaznacz rekord konta użytkownika.
4. Na liście w zaznaczonym wierszu kliknij łącze „Nazwa”, aby wyświetlić szczegółowe informacje o koncie użytkownika.
5. Kliknij kartę Zatrudnienie.
6. Rozwiń skróconą kartę rejestracji czasu, a następnie kliknij przycisk Aktywowanie na terminalach rejestracji.
7. Kliknij opcję Aktywowanie na terminalach rejestracji
8. W polu Grupa obliczania wprowadź lub wybierz wartość.
9. W polu Domyślna grupa obliczania wprowadź lub wybierz wartość.
10. W polu Grupa zatwierdzania wprowadź lub wybierz wartość.
11. W polu Profil standardowy wprowadź lub wybierz wartość.
12. W polu Grupa profilu wprowadź lub wybierz wartość.
13. Kliknij przycisk OK.
14. Kliknij przycisk Edytuj, aby wprowadzić numer karty identyfikacyjnej nowego pracownika odpowiedzialnego za rejestrację czasu.
15. W polu Identyfikator karty identyfikacyjnej wpisz wartość.
16. Kliknij przycisk Zapisz.
17. Użyj skrótu SaveRecord.
18. Zamknij stronę szczegółów pracownika.
19. Zamknij stronę.

## <a name="assign-worker-to-device-group"></a>Przypisywanie pracownika do grupy urządzeń
1. Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Wykonywanie produkcji > Konfiguruj kartę zadań dla urządzeń.
2. Kliknij przycisk Dodaj.
3. Na liście oznacz wybrany wiersz.
4. Kliknij przycisk OK.
5. Kliknij przycisk Edytuj.
6. W polu Jednostka produkcyjna można ustawić domyślny filtr dla pracownika. Daje to pewność, że gdy pracownik loguje się do urządzenia, wyświetlane są tylko zadania produkcyjne dla wybranej jednostki produkcyjnej.
7. Zamknij stronę.

