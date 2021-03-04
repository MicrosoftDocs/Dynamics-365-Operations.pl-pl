---
title: Użytkownicy usługi Attract nie mogą ubiegać się o pracę z portalu kariery
description: W tym temacie wyjaśniono sposób rozwiązania problemu polegającego na tym, że przyciąganie użytkowników nie może być stosowane do zadań z portalu kariery.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: e1d72bef6d8bbe15e27326f66341915ba44a09b4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462199"
---
# <a name="attract-users-cant-apply-for-jobs-from-career-portal"></a>Użytkownicy usługi Attract nie mogą ubiegać się o pracę z portalu kariery

[!include [banner](includes/banner.md)]

## <a name="issue"></a>Wystawienie

Użytkownicy usługi Attract nie mogą ubiegać się o pracę z portalu kariery. Przy próbie zastosowania się do zadania, które zostało utworzone w systemie Dynamics 365 Talent: Attract, przeglądarka ładuje stronę w sposób ciągły i nie powoduje wykonania tej akcji.

## <a name="cause"></a>Powód

Ten problem występuje, gdy zespół relacji talentów nie ma roli użytkownika talentów.

## <a name="resolution"></a>Rozdzielczość

Przypisz rolę użytkownika talentów do zespołu relacji talentów.

1. Zaloguj się do [Centrum administracyjnego Power Platform](https://admin.powerplatform.microsoft.com)z dowolnego z następujących poświadczeń administratora:

   - administrator Dynamics 365
   - Administrator globalny
   - Administrator Power Platform

2. W okienku nawigacji wybierz opcję **Środowiska**, a następnie wybierz środowisko, w którym chcesz przypisać rolę użytkownika talentów do zespołu relacji talentów.

   ![Wybierz środowisko](./media/attract-troubleshoot-career-portal-select-environment.png)

3. W **okienku środowiska** wybierz **adres URL środowiska** i zaloguj się do portalu administracyjnego środowiska (na przykład https: <orgname>. crm.dynamics.com).

4. Wybierz **Ustawienia**, wybierz opcję **System**, a następnie wybierz opcję **Zabezpieczenia**.

   ![Przejdź do sekcji Zabezpieczenia](./media/attract-troubleshoot-career-portal-security.png)

5. Wybierz pozycję **Zespoły**.

   ![Wybierz pozycję Zespoły](./media/attract-troubleshoot-career-portal-security-teams.png)

6. Wyszukaj **Zespół relacji talentów** w polu wyszukiwania, a następnie wybierz zespół z wyników wyszukiwania.

7. Wybierz opcję **ZARZĄDZAJ ROLAMI** ze wstążki.

8. W oknie dialogowym **Zarządzanie rolami zespołu** wybierz **Użytkownik talentów** z listy dostępnych ról opcję talentów użytkownika, a następnie kliknij przycisk **OK**, aby zastosować rolę.

   ![Zastosuj rolę](./media/attract-troubleshoot-career-portal-apply-role.png)

9. Przetestuj zmiany:

   1. Zaloguj się do portalu kariery w nowym oknie przeglądarki.
   2. Zastosuj do zadania z portalu kariery. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]