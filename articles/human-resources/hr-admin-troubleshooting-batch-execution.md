---
title: Resetowanie zablokowanych zadań wsadowych
description: W tym temacie opisano sposób rozwiązywania problemów związanych z zadaniami wsadowych, które są zablokowane.
author: twheeloc
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: f1aa9f53e0d314edd920a664d18408019325d435
ms.sourcegitcommit: d67f7edaf1a50077c2a7dd105e774f86fc586495
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2022
ms.locfileid: "8534029"
---
# <a name="reset-stuck-batch-jobs"></a>Resetowanie zablokowanych zadań wsadowych


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>Wystawienie

Microsoft Dynamics 365 Human Resources może mieć problemy z zadaniami wsadowym, które zablokowały się w stanie **Wykonywanie** lub **Anulowanie** i nie zostały ukończone.

## <a name="resolution"></a>Rozdzielczość

Gdy zadanie wsadowe znajduje się w stanie **Wykonywanie** lub **Anulowanie**, można zresetować stan, wymuś anulowanie zadania. Po jego anulowaniu można zresetować zadanie wsadowe, ustawiając dla niego stan **Oczekujące**. Zostanie on następnie ponownie uruchomiony w celu wykonania w następnym zaplanowanym uruchomieniu wsadowym.

1. W obszarze roboczym **Administrowanie systemem** wybierz stronę **Łącza** i wybierz **Zadania wsadowe**.

2. Na stronie listy **Zadań wsadowych** wybierz zadanie, które musi zostać zresetowane.

3. Na akcji na wstążce wybierz pozycję **Wymuszaj anulowanie** i potwierdź akcję.

   > [!NOTE]
   > Akcja **Wymuszaj anulowanie** jest dostępna tylko wtedy, gdy wybrane zadanie wsadowe ma stan **Wykonywanie** lub **Anulowanie** oraz nie są uruchomione żadne procesy wykonywania wsadowego ani anulowania dla tego zadania.

4. Na wstążce akcji wybierz opcję **Zmień stan**.

5. Na stronie **Wybierz nowy stan** wybierz pozycję **Oczekujące**, a następnie wybierz przycisk **OK**.

   ![Wybierz nowy stan zadania wsadowego.](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a>Informacje dodatkowe

[Aby zoptymalizować wydajność, należy zaplanować zadania wsadowe po godzinach](hr-admin-troubleshooting-batch-jobs.md)<br>
[Optymalizowanie wydajności za pomocą zadań automatycznego czyszczenia](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
