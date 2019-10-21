---
title: Osadzona aplikacja PowerApps w Dynamics 365 - Core HR
description: W tym temacie opisano, jak rozwiązać problem, gdzie element menu usługi PowerApps znika w module Administracja systemu.
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
ms.openlocfilehash: 4fbc24c5ceb73389b84b125eb942ac31757928aa
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008437"
---
# <a name="embed-powerapps-apps-in-core-hr"></a>Osadzone aplikacje PowerApps w Core HR

[!include [banner](includes/banner.md)]

**Wystawienie**

Element menu **PowerApps** zniknął z modułu **Administrowanie systemem**.

**Przyczyna**

Projekt interfejsu użytkownika został zmieniony, a Microsoft PowerApps zostanie dołączony do modelu standardowego personalizacji.

**Rozdzielczość**

Zmienił się sposób osadzenia usługi PowerApps. Aplikacje PowerApps teraz są dodawane za pomocą modelu personalizacji. Aplikacje PowerApps można dodać do prawie wszystkich stron w Microsoft Dynamics 365 Talent.

Aby uzyskać szczegółowe informacje o osadzaniu aplikacji PowerApps w Talents, zobacz [Osadzone PowerApps aplikacje](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

Odbiorcy PowerApps, którzy osadzili aplikacje przed zmianą powinni mieć uaktualniony system do nowego modelu.

Przycisk **PowerApps** znajduje się w prawym górnym rogu prawie każdej strony w Talent. Ten przycisk służy do wstawiania aplikacji PowerApps.

Oto przykład.

1. Przejdź do **zarządzania personelem \>łącza \>pracownicy \>pracownicy**.
2. Wybierz przycisk **PowerApps**, a następnie wybierz opcję **Wstaw PowerApp**.

    ![Przycisk PowerApps](media/png.png)

3. Wypełnij pola w oknie dialogowym **Wstaw PowerApp**.

    ![Okno dialogowe Wstaw PowerApp](media/insert-powerapp.png)

Można też wykonać następujące kroki.

1. W okienku akcji strony na karcie **Opcje** w grupie **Personalizacja** wybierz **Personalizuj ten formularz**.

    ![Personalizowanie grupy na karcie Opcje](media/options.png)

    Pojawi się pasek narzędzi personalizacji.

2. Na pasku narzędzi, wybierz **Wstaw \>PowerApp**.

    ![Wstawianie aplikacji PowerApps za pomocą paska narzędzi personalizacji](media/powerapp-bar.png)
