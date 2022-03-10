---
title: Diagnostyka zabezpieczeń dla nagrań zadań
description: Ten temat zawiera informacje o sposobach analizowania wymagań dotyczących uprawnień zabezpieczeń i zarządzania nimi na podstawie nagrania zadania.
author: Peakerbl
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 10.0.9
ms.openlocfilehash: 44af35f16f6e9ff89b30bc10eef3f16ecdfaf907c4c6e22aa5775d1941fb6a5d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6745127"
---
# <a name="security-diagnostics-for-task-recordings"></a>Diagnostyka zabezpieczeń dla nagrań zadań

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a>Przed rozpoczęciem

Ten temat zawiera informacje o sposobach analizowania wymagań dotyczących uprawnień zabezpieczeń i zarządzania nimi na podstawie nagrania zadania. Przed wykonaniem kroków opisanych w tym temacie należy utworzyć nagranie zadania procesu biznesowego do przeanalizowania. Aby zarejestrować proces biznesowy, zapoznać się z tematem [Zasoby rejestratora zadań](../../user-interface/task-recorder.md). 

## <a name="manage-security-for-a-task-recording"></a>Zarządzanie zabezpieczeniami na potrzeby nagrania zadania

1. Przejdź do pozycji **Administrowanie systemem** > **Zabezpieczenia** > **Diagnostyka zabezpieczeń na potrzeby nagrania zadania**.
2. Otwórz nagranie zadania z jego lokalizacji. Wybierz opcję **Otwórz z tego komputera** lub **Otwórz z usług Lifecycle Services**, a następnie wybierz pozycję **Zamknij**.
3. Spowoduje to otwarcie strony **Szczegóły elementu menu zabezpieczeń**, na której znajdują się obiekty zabezpieczeń wymagane w procesie.

 > [!NOTE]
 > Elementów **Akcja** i **Dane wyjściowe** nie ma na liście.

4. W polu **Identyfikator użytkownika** wybierz użytkownika. Jeśli użytkownik nie ma uprawnień do niektórych elementów menu, pole **Brakujące uprawnienia** zostanie zaktualizowane do wartości **Tak**.
  
  ![Strona szczegółów elementu menu zabezpieczeń.](../media/Security-Menu-Item-Details.png)

5. Wybierz pozycję **Dodaj odwołanie**, aby wyświetlić listę obiektów zabezpieczeń, w tym role, obowiązki i uprawnienia, które przyznają brakujące uprawnienie.
6. Wybierz obiekt zabezpieczeń z listy:

    - Jeśli wybrano pozycję **Rola**, wybierz opcję **Dodaj rolę do użytkownika**. Spowoduje to otwarcie strony **Przypisywanie użytkowników do ról**. Więcej informacji można znaleźć na stronie [Przypisywanie użytkowników do ról zabezpieczeń](assign-users-security-roles.md).
    - Jeśli wybrano pozycję **Obowiązek**, wybierz opcję **Dodaj obowiązek do roli**, wybierz role, do których ma zostać dodany obowiązek, a następnie wybierz przycisk **OK**.
    - Jeśli wybrano pozycję **Uprawnienie**, wybierz opcję **Dodaj uprawnienie do obowiązków**, wybierz role, do których ma zostać dodany obowiązek, a następnie wybierz przycisk **OK**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]