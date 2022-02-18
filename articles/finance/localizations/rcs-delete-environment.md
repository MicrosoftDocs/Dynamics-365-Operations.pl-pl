---
title: Usługa Regulatory Configuration Service (RCS) — usuwanie środowiska RCS
description: Ten temat wyjaśnia, jak administrator systemu Regulatory Configuration Service (RCS) może usunąć środowisko RCS i związane z nim dane.
author: JaneA07
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Global
audience: Application User, System Admin
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: f9073a14143423676f23f9bf8dc9c17dbae18a6c3ad0d2f6d1e33919fd9162bf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759826"
---
# <a name="regulatory-configuration-service-rcs---delete-an-rcs-environment"></a>Usługa Regulatory Configuration Service (RCS) — usuwanie środowiska RCS

[!include [banner](../includes/banner.md)]

Ten temat wyjaśnia, jak administrator systemu Regulatory Configuration Service (RCS) może usunąć środowisko RCS i związane z nim dane.

Przed wykonaniem procedury opisanej w tym temacie muszą być spełnione następujące warunki wstępne:

- Musisz mieć przypisaną rolę **Administrator systemu** dla środowiska RCS.
- Rola **System Admin** musi mieć przypisaną rolę **RCSDeleteEnvironmentDuty**.

## <a name="delete-an-rcs-environment"></a>Usuwanie środowiska RCS

1. Otwórz RCS wybierz kafelek roboczy **Raportowanie elektroniczne**.
2. W sekcji **Łącza pokrewne** wybierz opcję **Usuń środowisko z RCS**.

    ![Usuń łącze do środowiska RCS w sekcji Powiązane łącza.](media/01_RCS-Delete-Environ-Related-Link.PNG)

3. W oknie dialogowym, które się pojawi, przejrzyj komunikaty o zakresie usuwania środowiska.

    ![Komunikaty w oknie dialogowym Usuń środowisko RCS.](media/01_RCS-Delete-Environ-Msg_noGUID.PNG)

    > [!IMPORTANT]
    > Nie można wycofać usunięcia środowiska RCS.
    >
    > Operacja usuwa wybrane środowisko RCS i wszelkie powiązane z nim dane, w tym cechy i konfiguracje, które są przechowywane w repozytorium globalnym. Cechy i konfiguracje, które są współdzielone z innymi organizacjami, zostaną usunięte, jeśli nie mają żadnych zależności. Funkcje i konfiguracje, które posiadają zależności zostaną oznaczone jako wycofane z użycia.

4. W polu, które się pojawi, wpisz globalnie unikalny identyfikator (GUID) środowiska RCS, by potwierdzić, że chcesz je usunąć. Identyfikator GUID środowiska jest dołączany do wiadomości o usunięciu.
5. Wybierz **Usuń środowisko**.
    
Twoje środowisko RCS i wszelkie związane z nim dane są teraz usuwane.

> [!IMPORTANT]
> Po usunięciu środowiska RCS, nie ma sposobu na odzyskanie danych. Nowe środowisko RCS może być utworzone w każdym dostępnym regionie RCS.