---
title: Pracownicy bez zatrudnienia
description: Pracownicy bez przyszłego, aktywnego lub historycznego zatrudnienia w Twojej organizacji pojawiają się na stronie Pracownicy bez zatrudnienia.
author: twheeloc
ms.date: 11/03/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0b8fe7dd0818fa1c3cc4224e73035849f9dadfe
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070558"
---
# <a name="workers-without-employment"></a>Pracownicy bez zatrudnienia


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Pracownicy, którzy nie mają żadnego przyszłego, aktywnego ani przeszłego zatrudnienia w Twojej organizacji, pojawiają się na stronie **Pracownicy bez zatrudnienia**. Pracownicy z tym stanem mogą pojawiać się podczas importowania pracowników bez rekordu zatrudnienia lub usuwania zatrudnienia pracownika za pośrednictwem opcji **Pracownicy \> Historia zatrudnienia**.

Domyślnie strona **Pracownicy bez zatrudnienia** jest dostępna dla następujących ról:

- Asystent ds. kadr
- Menedżer ds. kadr
- Osoba rekrutująca
- Menedżer wynagrodzeń i świadczeń
- Administrator listy płac
- Menedżer ds. listy płac
- Menedżer ds. szkoleń

Z listy **Pracownicy bez zatrudnienia** można usunąć osoby. Domyślnie to uprawnienie jest nadane roli Asystent ds. kadr. To uprawnienie można udzielić innym rolom, wykonując następujące kroki:

1. Wybierz opcję **Administrowanie systemem**, a następnie wybierz opcję **Konfiguracja zabezpieczeń**.

2. Na karcie **uprawnienia** odfiltruj listę **uprawnień**, aby **obsługiwać pracowników**.

   [![Filtrowanie listy uprawnień.](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)

3. W kolumnie **odwołania** wybierz **Wyświetl elementy menu**.

4. W kolumnie **Wyświetl elementy menu** wybierz **HcmWorkersWithoutEmployment**.

   [![Wybierz formularz.](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)

5. Zmień ustawienie uprawnienia **Usuń** na **Udzielenie**.

6. Wybierz kartę **nieopublikowane obiekty**.

7. Wybierz opcję **Publikuj wszystko**.

   [![Opublikuj zmiany.](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
