---
title: Usługa Regulatory Configuration Service (RCS) — usuwanie środowiska RCS
description: Ten artykuł wyjaśnia, jak administrator systemu Regulatory Configuration Service (RCS) może usunąć środowisko RCS i związane z nim dane.
author: kfend
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, System Admin
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.15
ms.custom: 97423
ms.assetid: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Global
ms.openlocfilehash: bdcb6820ead72fce0f89bf80cc5e474cb3942724
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277249"
---
# <a name="regulatory-configuration-service-rcs---delete-an-rcs-environment"></a>Usługa Regulatory Configuration Service (RCS) — usuwanie środowiska RCS

[!include [banner](../includes/banner.md)]

Ten artykuł wyjaśnia, jak administrator systemu Regulatory Configuration Service (RCS) może usunąć środowisko RCS i związane z nim dane.

Przed wykonaniem procedury opisanej w tym artykule muszą być spełnione następujące warunki wstępne:

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
