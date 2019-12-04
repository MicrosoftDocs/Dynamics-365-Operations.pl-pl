---
title: Osadzona aplikacja Power Apps w Dynamics 365 - Core HR
description: W tym temacie opisano, jak rozwiązać problem, gdzie element menu usługi Microsoft Power Apps znika w module Administracja systemu.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6d1b7f1dd71e6bcbf10c4d91fe33e9494b041a2c
ms.sourcegitcommit: ae0efac749ab34d423fac44d00a597801c143fbb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/22/2019
ms.locfileid: "2830216"
---
# <a name="embed-power-apps-apps-in-dynamics-365---core-hr"></a>Osadzona aplikacja Power Apps w Dynamics 365 - Core HR

[!include [banner](includes/banner.md)]

**Wystawienie**

Element menu **Power Apps** zniknął z modułu **Administrowanie systemem**.

**Przyczyna**

Projekt interfejsu użytkownika został zmieniony, a Microsoft Power Apps zostanie dołączony do modelu standardowego personalizacji.

**Rozdzielczość**

Zmienił się sposób osadzenia usługi Power Apps. Power Apps teraz są dodawane za pomocą modelu personalizacji. Power Apps można dodać do prawie wszystkich stron w Microsoft Dynamics 365 Talent.

Aby uzyskać szczegółowe informacje o osadzaniu aplikacji Power Apps w Talents, zobacz [Osadzone Microsoft Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

Odbiorcy Power Apps, którzy osadzili aplikacje przed zmianą powinni mieć uaktualniony system do nowego modelu.

Przycisk **Power Apps** znajduje się w prawym górnym rogu prawie każdej strony w Talent. Ten przycisk służy do wstawiania Power Apps.

Oto przykład.

1. Przejdź do **zarządzania personelem \>łącza \>pracownicy \>pracownicy**.
2. Wybierz przycisk **Power Apps**, a następnie wybierz opcję **Wstaw PowerApp**.

    ![Przycisk Power Apps](media/png.png)

3. Wypełnij pola w oknie dialogowym **Wstaw PowerApp**.

    ![Okno dialogowe Wstaw PowerApp](media/insert-powerapp.png)

Można też wykonać następujące kroki.

1. W okienku akcji strony na karcie **Opcje** w grupie **Personalizacja** wybierz **Personalizuj ten formularz**.

    ![Personalizowanie grupy na karcie Opcje](media/options.png)

    Pojawi się pasek narzędzi personalizacji.

2. Na pasku narzędzi, wybierz **Wstaw \>PowerApp**.

    ![Wstawianie aplikacji Power Apps za pomocą paska narzędzi personalizacji](media/powerapp-bar.png)
