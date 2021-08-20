---
title: Instalowanie dodatku Analiza Internetu rzeczy (IoT) w usługach LCS
description: W tym temacie objaśniono, jak zainstalować dodatek analizy Internetu rzeczy (IoT) w usługach Microsoft Dynamics Lifecycle Services (LCS).
author: robinarh
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c4727f4341104b77838c103fcf378a5971f8ba176f18c2d32d619ecd6614b1ae
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736826"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a>Instalowanie dodatku Analiza Internetu rzeczy (IoT) w usługach LCS

[!include [banner](../../includes/banner.md)]

W tym temacie objaśniono, jak zainstalować dodatek analizy Internetu rzeczy (IoT) w usługach Microsoft Dynamics Lifecycle Services (LCS). Należy zauważyć, że dodatki nie mogą być instalowane w środowisku demonstracyjnym/próbnym. Aby można było zainstalować dodatek, trzeba [utworzyć zasoby platformy Azure](iot-azure-setup.md).

## <a name="set-up-the-lcs-environment"></a>Konfigurowanie środowiska usług LSC

1. Otwórz usługi LCS i przejdź do swojego środowiska Microsoft Dynamics 365 Supply Chain Management.
2. Przewiń w dół do sekcji **Dodatki środowiska**.
3. Wybierz pozycję **Zainstaluj nowy dodatek**, aby wyświetlić listę dodatków, które zostały włączone dla środowiska.
4. W oknie dialogowym **Wybieranie dodatku do zainstalowania** wybierz pozycję **Analiza Internetu rzeczy (IoT)**.
5. W oknie dialogowym **konfigurowania dodatku** podaj szczegóły dotyczące centrum IoT i pamięci podręcznej Redis. Wymagane wartości można znaleźć w magazynie kluczy utworzonym podczas [tworzenia zasobów platformy Azure](iot-azure-setup.md).

    + **Identyfikator dzierżawy** — w witrynie Azure Portal przejdź do magazynu kluczy, a następnie w lewym okienku nawigacji wybierz pozycję **Przegląd** i skopiuj wartość **identyfikatora katalogu**. Wklej tę wartość w oknie dialogowym **konfigurowania dodatku**.
    + **Identyfikator URI magazynu kluczy punktów końcowych zgodnych z centrum zdarzeń IoT** — przejdź do magazynu kluczy, a następnie w lewym okienku nawigacji wybierz pozycję **Przegląd** i skopiuj wartość **nazwy DNS**. Wklej tę wartość w oknie dialogowym **konfigurowania dodatku**.
    + **Nazwa klucza tajnego punktu końcowego zgodnego z centrum zdarzeń IoT** — przejdź do magazynu kluczy, a następnie w lewym okienku nawigacji wybierz pozycję **Klucze tajne** i skopiuj nazwę klucza tajnego, w którym są przechowywane parametry połączenia centrum IoT. Wklej tę wartość w oknie dialogowym **konfigurowania dodatku**.
    + **Identyfikator URI magazynu kluczy pamięci podręcznej Redis** — przejdź do magazynu kluczy, a następnie w lewym okienku nawigacji wybierz pozycję **Przegląd** i skopiuj wartość **nazwy DNS**. Wklej tę wartość w oknie dialogowym **konfigurowania dodatku**.
    + **Nazwa klucza tajnego punktu końcowego pamięci podręcznej Redis** — przejdź do magazynu kluczy, a następnie w lewym okienku nawigacji wybierz pozycję **Klucze tajne** i skopiuj nazwę klucza tajnego, w którym jest przechowywana pamięć podręczna Redis. Wklej tę wartość w oknie dialogowym **konfigurowania dodatku**.

6. Zaznacz pole wyboru, aby zaakceptować warunki i postanowienia.
7. Wybierz **Zainstaluj**.
8. Zostanie wyświetlone okno komunikatu z informacją o tym, że „Dodatek został pomyślnie wyzwolony w celu instalacji”. Kliknij przycisk **OK**.

Konfiguracja usługi LCS jest teraz zakończona. Następnym krokiem jest [skonfigurowanie scenariuszy](iot-scenario-setup.md).

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a>Odinstalowywanie dodatku

1. [Wyłącz scenariusze](iot-scenario-setup.md#disable-a-scenario) w aplikacji Supply Chain Management.
2. W usługach LCS przejdź do szczegółów środowiska Supply Chain Management.
3. Przewiń w dół do sekcji **Dodatki środowiska**.
4. Wybierz pozycję **Odinstaluj** dla dodatku analizy Internetu rzeczy (IoT).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]