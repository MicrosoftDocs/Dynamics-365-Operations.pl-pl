---
title: Konfigurowanie decyzji warunkowych w przepływie pracy
description: Procedura zamieszczona poniżej umożliwia skonfigurowanie właściwości decyzji warunkowej.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ed53eeb26e1b4b1df1647739ce1d115c7dd169f8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747938"
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