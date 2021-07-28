---
title: Pracownicy bez zatrudnienia
description: Pracownicy bez przyszłego, aktywnego lub historycznego zatrudnienia w organizacji są wyświetlani w formularzu Pracownicy bez zatrudnienia.
author: andreabichsel
ms.date: 04/06/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 71cb119e533e64b14badf65f55e8c4d5aa4c4b2f
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356591"
---
# <a name="workers-without-employment"></a>Pracownicy bez zatrudnienia

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Pracownicy bez przyszłego, aktywnego lub historycznego zatrudnienia w organizacji są wyświetlani w formularzu **Pracownicy bez zatrudnienia**. Pracownicy z tym stanem mogą pojawiać się podczas importowania pracowników bez rekordu zatrudnienia lub usuwania zatrudnienia pracownika za pośrednictwem opcji **Pracownicy > Historia zatrudnienia**.

Domyślnie formularz **Pracownicy bez zatrudnienia** jest dostępny dla następujących ról:

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