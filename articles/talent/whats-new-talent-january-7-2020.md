---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (7 stycznia 2020 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/07/2020
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
ms.search.validFrom: 2020-01-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e227c614fdbfe6f3dd410f1a533c593979abf1ec
ms.sourcegitcommit: 615ed3e4260192ba36826e128f1afa1588e94845
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/21/2020
ms.locfileid: "2974437"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-7-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (7 stycznia 2020 r.)

W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2697. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).

 
### <a name="cant-delete-workers-that-dont-have-employment-records---386157"></a>Nie można usunąć pracowników, którzy nie mają rekordów zatrudnienia — (386157)

Ta zmiana powoduje dodanie opcji usuwania w formularzu **pracownicy bez zatrudnienia**. Pracownicy są wyświetlani w tym formularzu, gdy dla pracownika nie istnieją przyszłe, aktywne lub historyczne zatrudnienia. W tej wersji funkcja usuwania jest włączona tylko dla administratorów systemu. Jednak w przyszłotygodniowym wydaniu zabezpieczenia zostaną zaktualizowane, aby umożliwić wszystkim użytkownikom z rolą asystenta działu kadr usuwanie pracowników bez zatrudnienia. Zmiany te można również wprowadzić ręcznie, wykonując następujące kroki:

1. Przejdź do **Konfiguracja zabezpieczeń**.
2. Na karcie **uprawnienia** odfiltruj listę **uprawnień**, aby **obsługiwać pracowników**.
3. W kolumnie **odwołania** wybierz **Wyświetl elementy menu**.
4. W kolumnie **Wyświetl elementy menu** wybierz **HcmWOrkersWithoutEmployment**.
5. Ustaw zezwolenie na **usuwanie**.
6. Wybierz kartę **nieopublikowane obiekty**.
7. Wybierz opcję **Publikuj wszystko**.
