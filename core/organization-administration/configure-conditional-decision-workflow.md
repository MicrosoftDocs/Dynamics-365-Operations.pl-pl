---
title: "Konfigurowanie decyzji warunkowej w przepływie pracy"
description: "Procedura zamieszczona poniżej umożliwia skonfigurowanie właściwości decyzji warunkowej."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 3bba3d849d02cd84c2c0e0c5c15f7b649b3e125c
ms.lasthandoff: 03/31/2017


---

# <a name="configure-a-conditional-decision-in-a-workflow"></a>Konfigurowanie decyzji warunkowej w przepływie pracy

Procedura zamieszczona poniżej umożliwia skonfigurowanie właściwości decyzji warunkowej.

Decyzja warunkowa to punkt, w którym przepływ pracy rozdziela się na dwie gałęzie. Aby skonfigurować decyzję warunkową, w edytorze przepływu pracy kliknij decyzję warunkową prawym przyciskiem myszy i wybierz polecenie **Właściwości**, a zostanie otwarta formularz **Właściwości**.

## <a name="name-a-decision"></a>Nazywanie decyzji
Wykonaj następujące kroki, aby nazwać decyzję warunkową.
1.  W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2.  W polu **Nazwa** wprowadź unikatową nazwę decyzji warunkowej.

## <a name="set-conditions"></a> Konfigurowanie warunków
System decyduje, której gałęzi użyć, oceniając przesłany dokument, aby ustalić, czy spełnia określone warunki.
1.  W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
2.  Click **Add condition**.
3.  Służy do wprowadzania warunku.
4.  Wprowadź dodatkowe warunki, jeśli są wymagane.
5.  Aby sprawdzić, czy wprowadzone warunki są poprawnie skonfigurowane, wykonaj następujące czynności:
    1.  Kliknij opcję **Testuj**, a zostanie otwarty formularz **Warunek testowy przepływu pracy**.
    2.  Wybierz rekord w obszarze **Sprawdź poprawność warunku** formularza.
    3.  Kliknij przycisk **Test**. System oszacuje rekord i określi, czy rekord spełnia określone warunki.
    4.  Kliknij **OK** lub **anulowanie** aby powrócić do **właściwości** formularza.




