---
title: Instalowanie dodatku Analiza Internetu rzeczy (IoT) w usługach LCS
description: W tym artykule objaśniono, jak zainstalować dodatek analizy Internetu rzeczy (IoT) w usługach Microsoft Dynamics Lifecycle Services (LCS).
author: johanhoffmann
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 52fe4c4a79378aca5f1e64c8b3f4fa85199c9911
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887494"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a>Instalowanie dodatku Analiza Internetu rzeczy (IoT) w usługach LCS

[!include [banner](../../includes/banner.md)]

W tym artykule objaśniono, jak zainstalować dodatek analizy Internetu rzeczy (IoT) w usługach Microsoft Dynamics Lifecycle Services (LCS). Należy zauważyć, że dodatki nie mogą być instalowane w środowisku demonstracyjnym/próbnym. Aby można było zainstalować dodatek, trzeba [utworzyć zasoby platformy Azure](iot-azure-setup.md).

Analizę IoT można konfigurować bez pisania kodu. Oto podstawowe kroki.

1. [Skonfiguruj zasoby platformy Azure](iot-azure-setup.md) — utwórz centrum IoT, pamięć podręczną Redis i magazyn kluczy, które będą dostępny z poziomu aplikacji Supply Chain Management.
2. [Formaty schematu wiadomości dla usługi IoT Hub](iot-schema-format.md) — skonfiguruj urządzenia do wysyłania wiadomości do usługi IoT Hub oraz zdefiniuj format komunikatu JSON (JavaScript Object Notation).
3. W zarządzaniu funkcjami włącz flagę funkcji analizy IoT.
4. Zainstaluj dodatek analizy IoT w usłudze Microsoft Dynamics Lifecycle Services (LCS) – zainstaluj ten dodatek w usłudze LCS i skonfiguruj wpisy tajne platformy Azure (jak opisano w tym artykule).
5. [Skonfiguruj metryki](iot-metrics-setup.md) — skonfiguruj metryki w aplikacji Supply Chain Management.
6. [Skonfiguruj scenariusz](iot-scenario-setup.md) — skonfiguruj scenariusze w aplikacji Supply Chain Management.

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