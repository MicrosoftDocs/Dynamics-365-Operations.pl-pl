---
title: Ustaw kody przyczyn
description: W programie Dynamics 365 Human Resources kody przyczyn są używane do wyjaśniania, dlaczego świadczenia dla pracownika się zmieniają.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ee74cb8b11c9b72940448077ee485ade4c0b7a39
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801054"
---
# <a name="set-up-reason-codes"></a>Ustaw kody przyczyn

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W programie Dynamics 365 Human Resources kody przyczyn są używane do wyjaśniania, dlaczego świadczenia dla pracownika się zmieniają.

> [!NOTE]
> W styczniu 2021 r. kody przyczyn są migrujące do obszaru roboczego **Zarządzanie pracownikami**, a nie do obszaru roboczego **Zarządzanie świadczeniami**. Aby uzyskać więcej informacji, zobacz [Ręczna migracja kodów przyczyny do zarządzania personelem](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).

## <a name="create-reason-codes"></a>Tworzenie kodów przyczyn

1. W obszarze roboczym **Zarządzanie pracownikami** (lub obszarze roboczym **Zarządzanie świadczeniami**, jeśli kody przyczyn nie zostały jeszcze poddane migracji), wybierz opcję **Łącza**, a następnie wybierz pozycję **Kody przyczyn**.

2. Wybierz pozycję **Nowy**.

3. Określ wartości dla następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Kod przyczyny** | Unikatowa nazwa identyfikująca przyczynę, dla której pracownik etatowy zmienia rejestrację na inny plan świadczeń. |
   | **Opis** | Opis kodu przyczyny. |

4. W **Odpowiednich scenariuszach** ustaw wartość **Zarządzanie świadczeniami** na **Tak**. (Nie dotyczy, jeśli kody przyczyn nie zostały jeszcze zmigrowane do obszar roboczy **Zarządzanie pracownikami**.)

5. Wybierz opcję **Zapisz**.

## <a name="manually-migrate-reason-codes-to-personnel-management"></a>Ręczna migracja kodów przyczyny do zarządzania personelem

W styczniu 2021 r. kody przyczyn są migrujące do obszaru roboczego **Zarządzanie pracownikami**, a nie do obszaru roboczego **Zarządzanie świadczeniami**. Większość danych kodu przyczyny zostanie automatycznie przeniesiona do Twojego środowiska. Niektóre dane kodu przyczyny mogą nie być przenoszone. Na przykład kody przyczyn mają teraz maksymalnie 15 znaków, więc żadne kody przyczyn dłuższe niż 15 znaków nie zostaną automatycznie przeniesione.

Na stronie **Łącza** w obszarze roboczym **Zarządzanie świadczeniami** zostanie wyświetlony transparent informjący o migracji i o tym, czy jakieś kody przyczyn nie były migrowane.

1. Wybierz **Kody przyczyn**, aby uzyskać szczegółowe informacje o stanie migracji.

   [![Kody przyczyn](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)

2. Wybierz kod przyczyny, który nie został migrowany.

   [![Stan migracji kodu przyczyny](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)

3. Wybierz opcję **Migracja kodu przyczyny**.

   [![Dokonaj migracji kodu przyczyny](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)

4. W okienku **Migracja kodu przyczyny świadczenia** dostępne są dwie opcje mapowania na kod przyczyny zarządzania pracownikami:

   - Aby użyć istniejącego kodu przyczyny w zarządzaniu pracownikami, wybierz go z listy rozwijanej **Użyj istniejącego kodu przyczyny**.
     > [!NOTE]
     > Możesz użyć istniejącego kodu przyczyny w zarządzaniu personelem tylko wtedy, gdy inny kod przyczyny zarządzania świadczeniami nie został już do niego migrowany.
   - Aby utworzyć nowy kod przyczyny w zarządzaniu pracownikami, wprowadź nowy w polu **Nowy kod przyczyny**, a następnie wprowadź opis w polu **Nowy opis**.

   [![Mapuj na kod przyczyny zarządzania pracownikami](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)

Po migrowania kodów przyczyny do funkcji Zarządzania pracownikami opcja używania tych kodów w zarządzaniu świadczeniami jest automatycznie ustawiana na **Tak**.

[![Użyj kodu przyczyny w zarządzaniu świadczeniami](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]