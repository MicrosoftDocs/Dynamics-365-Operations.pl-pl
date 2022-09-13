---
title: Anulowanie pracy magazynowej na potrzeby obsługi wyjątków
description: W tym artykule opisano funkcję anulowania pracy, która pozwala kierownikom magazynu na obsługę zablokowanej pracy.
author: Mirzaab
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSTroubIeshootingSeIfService, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b1e2036e4e7a8a47d6df029f285df7aca0fa74e6
ms.sourcegitcommit: 0220be95c007c77ba3b73fed8ac68a3d72dc2884
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2022
ms.locfileid: "9403710"
---
# <a name="cancel-warehouse-work-for-exception-handling"></a>Anulowanie pracy magazynowej na potrzeby obsługi wyjątków

[!include [banner](../includes/banner.md)]

Funkcja anulowania pracy w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management umożliwia administratorowi anulowanie konkretnej pracy magazynowej, która jest obecnie w toku, ale która została zablokowana przez system lub nie może zostać zakończona z powodu wyjątkowych okoliczności. Ta funkcja to atrakcyjna i bezpieczna alternatywa dla skryptów korygujących SQL, które rozwiązują problemy z niespójnymi danymi. Do obsługi tych skryptów są jednak zazwyczaj niezbędni informatycy, a funkcja anulowania pracy może być używana w firmie przez użytkowników z uprawnieniami administratora.

Aby uzyskać dostęp do funkcji anulowania pracy, możesz przejść do obszaru **Zarządzanie magazynem** \> **Zadania okresowe** \> **Oczyszczanie \> Anuluj pracę**. W oknie dialogowym **Anulowanie pracy** określ identyfikator pracy do anulowania, a następnie wybierz przycisk **OK**.

## <a name="warehouse-work-that-can-be-canceled"></a>Praca magazynowa, którą można anulować

Podczas operacji pobrania z magazynu pracownik może napotkać sytuacje, w których ilości zostały zarejestrowane jako pobrane z lokalizacji magazynu do lokalizacji użytkownika, ale nie można zarejestrować operacji odłożenia. Niespójne dane magazynu są często, ale nie zawsze, przyczyną zablokowania pracy.

W odróżnieniu od zwykłej funkcji anulowania, z której można skorzystać za pomocą przycisku **Anuluj** w nagłówku pracy, funkcja anulowania pracy nie wymaga, aby ostatni zakończony wiersz pracy miał typem pracy **Odłożenie**. Mówiąc inaczej, w przypadku funkcji anulowania pracy można uruchomić logikę anulowania, nawet jeśli ilość pozycji w wierszu pracy znajduje się w lokalizacji użytkownika.

> [!NOTE]
> W przypadku pracy, którą trzeba anulować z przyczyn operacyjnych, użytkownicy magazynu muszą nadal korzystać ze zwykłej funkcji anulowania na stronie pracy.

Za pomocą funkcji anulowania pracy można anulować tylko pracę następującego typu: **Sprzedaż**, **Wydanie przeniesienia**, **Pobranie zapasów** lub **Uzupełnianie zapasów**. Logika anulowania nie zostanie uruchomiona dla zamrożonej pracy pobrania surowca lub pracy, którą można anulować za pomocą zwykłej funkcji anulowania (zobacz poprzednią notatkę).

Aby odblokować pracę, system anuluje wszystkie pozostałe wiersze pracy i naprawia dane magazynu skojarzone z określonym przez użytkownika identyfikatorem pracy. Następnie można wznowić wszystkie zwykłe operacje obsługi magazynu, które obejmują uwzględnioną ilość pozycji.

Aby umieścić uwzględnioną pozycję w określonej lokalizacji po anulowaniu pracy, użytkownik musi skorzystać z operacji przeniesienia zapasów lub korekty ilości na urządzeniu przenośnym.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]