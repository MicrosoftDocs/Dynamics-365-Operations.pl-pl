---
title: Konfigurowanie decyzji warunkowych w przepływie pracy
description: Procedura zamieszczona poniżej umożliwia skonfigurowanie właściwości decyzji warunkowej.
author: ChrisGarty
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 957246ac9a758de9f420b9c672520dcb07c43a69
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693961"
---
# <a name="configure-conditional-decisions-in-a-workflow"></a>Konfigurowanie decyzji warunkowych w przepływie pracy

[!include [banner](../includes/banner.md)]

Procedura zamieszczona poniżej umożliwia skonfigurowanie właściwości decyzji warunkowej.

Decyzja warunkowa to punkt, w którym przepływ pracy rozdziela się na dwie gałęzie. Aby skonfigurować decyzję warunkową, w edytorze przepływu pracy kliknij decyzję warunkową prawym przyciskiem myszy i wybierz polecenie **Właściwości**, a zostanie otwarta formularz **Właściwości**.

## <a name="name-a-decision"></a>Nazywanie decyzji

Wykonaj następujące kroki, aby nazwać decyzję warunkową.

1. W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2. W polu **Nazwa** wprowadź unikatową nazwę decyzji warunkowej.

## <a name="set-conditions"></a> Konfigurowanie warunków

System decyduje, której gałęzi użyć, oceniając przesłany dokument, aby ustalić, czy spełnia określone warunki.

1. W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2. Kliknij opcję **Dodaj warunek**.
3. Służy do wprowadzania warunku.
4. Wprowadź dodatkowe warunki, jeśli są wymagane.
5. Aby sprawdzić, czy wprowadzone warunki są poprawnie skonfigurowane, wykonaj następujące czynności:

    1. Kliknij opcję **Testuj**, a zostanie otwarty formularz **Warunek testowy przepływu pracy**.
    2. Wybierz rekord w obszarze **Sprawdź poprawność warunku** formularza.
    3. Kliknij przycisk **Test**. System oszacuje rekord i określi, czy rekord spełnia określone warunki.
    4. Kliknij przycisk **OK** lub **Anuluj**, aby powrócić do formularza **Właściwości**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]