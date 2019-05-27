---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (23 stycznia 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/23/2019
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
ms.author: dkrame
ms.search.validFrom: 2019-01-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f27698c257301f52e5c77eaa8a04ca13a0315825
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518809"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-january-23-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent Core HR (23 stycznia 2019 r.)

[!include [banner](includes/banner.md)]

**Kompilacja 8.1.2121**

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Core HR.

## <a name="changes"></a>Zmiany

### <a name="import-of-employee-fixed-compensation-not-working-when-creating-new-fixed-compensation-records"></a>Import stałego wynagrodzenia pracownika nie działa podczas tworzenia nowych rekordów stałego wynagrodzenia
Dokonano zmian wpisu stałego wynagrodzenia pracownika, aby pobierał poziom wynagrodzenia podczas importowania. Przed tą wersją wyświetlany był komunikat wskazujący, że wymagany jest poziom.

### <a name="remove-the-minimum-balance-field-from-the-time-off-request-dialog-box"></a>Usunięto pole minimalnego salda z pola dialogowego żądania czasu wolnego
Pole **Minimalne saldo** zostało usunięte z okna dialogowego **Żądanie czasu wolnego**. Ta zmiana ma wpływ na wszystkie obszary, w których można zażądać czasu wolnego od pracy.

### <a name="data-upgrade-for-compensation-levels-not-updating-in-all-scenarios"></a>Zaktualizowano dane dla poziomów wynagrodzeń, które nie aktualizują się we wszystkich scenariuszach
Zmiana została dokonana celem aktualizacja poziomu wynagrodzeń dla planów stałych wynagrodzeń. Ta zmiana spowoduje wypełnienie poziomu wynagrodzenia w stałych planach dla stanowiska przypisanego pracownikowi.

### <a name="payroll-information-in-the-manage-changes-page-is-only-available-when-logged-in-as-system-administrator"></a>Informacja o liście płac na stronie Zarządzaj zmianami jest dostępna tylko po zalogowaniu się jako Administrator systemu
Ta zmiana daje pracownikom z rolą Administratora listy płat dostęp do informacji o liście płac na stronie **Oś czasu zmian > Zarządzaj zmianami** dla stanowiska.

### <a name="job-fields-default-to-positions"></a>Pola zadań przyjmują domyślnie wartości stanowiska
Po zmianie zadania na stanowisku pola zadania domyślnie przyjmują wartość stanowiska. Wyświetlony zostanie komunikat z opcją zaakceptowania domyślnych wartości lub zachowania istniejących wartości tych pól.

### <a name="probation-period-and-calendar-are-not-displayed-for-future-hired-employees"></a>Okres próbny i kalendarz nie są wyświetlane dla przyszłych zatrudnionych pracowników.
Po wprowadzeniu tej zmiany pola **Okres próbny** i **Kalendarz** zostały dodane do strony **Zarządzanie zmianami**, aby umożliwić wprowadzanie danych dla przyszłych i przeszłych pracowników.

### <a name="platform-update-23"></a>Aktualizacja platformy Update 23
Aktualizacja platformy 23 zawiera drobne poprawki błędów. Aby uzyskać więcej informacji, zobacz [Nowości i zmiany na platformie Dynamics 365 for Finance and Operations w aktualizacji 23 (styczeń 2019 r.)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23). 
