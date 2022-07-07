---
title: Dodawanie adresu do zlecenia serwisowego
description: W tym artykule opisano sposób dodawania adresu odbiorcy do zlecenia serwisowego.
author: sorenva
ms.date: 06/15/2020
ms.topic: article
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c485c50bab7c2e945aa0f0fc0601008dcebd3328
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015733"
---
# <a name="add-an-address-to-a-service-order"></a>Dodawanie adresu do zlecenia serwisowego

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób dodawania adresu odbiorcy do zlecenia serwisowego. Podczas tworzenia zlecenia serwisowego informacje adresowe są przenoszone z projektu, do którego jest dołączone zlecenie serwisowe. Jednak można wybrać alternatywną lokalizację z adresów, które zostały już wprowadzone w Microsoft Dynamics AX dla odbiorców, dostawców, oddziałów, magazynów, zleceń serwisowych i projektów.

Można również utworzyć nowy adres. Domyślnie nowy adres zostanie przeniesiony do projektu. Można jednak określić, że nowy adres jest odpowiedni tylko dla tego wystąpienia usługi. W takim przypadku nowy adres nie zostanie przeniesiony do projektu.

## <a name="create-a-customer-address-for-a-service-order"></a>Tworzenie adresu odbiorcy dla zlecenia serwisowego

Aby dodać adres do zlecenia serwisowego, wykonaj następujące czynności:

1. Przejdź do **Zarządzanie serwisem** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.

1. Otwórz zlecenie serwisowe, dla którego chcesz utworzyć adres.

1. Otwórz kartę **Nagłówek**.

1. Rozwiń skróconą kartę **Adres**, a następnie wybierz pozycję **Dodaj adres** na pasku narzędzi Skrócona karta.

1. W oknie dialogowym **Nowy adres** wprowadź niepowtarzalną nazwę dla adresu i wypełnij pozostałe pola. 

    > [!WARNING]
    > Jeśli wprowadzisz taką samą nazwę jak istniejący adres, informacje wprowadzone w pozostałych polach zastąpią informacje istniejącego adresu.

1. Wybierz **OK**, aby skopiować nowy adres do zlecenia serwisowego.

## <a name="specify-an-alternative-address-on-a-service-order"></a>Określanie adresu alternatywnego dotyczącego zlecenia serwisowego

Aby dodać inny adres do zlecenia serwisowego, wykonaj następujące czynności:

1. Przejdź do **Zarządzanie serwisem** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.

1. Otwórz zlecenie serwisowe, dla którego chcesz wprowadzić inny adres.

1. Otwórz kartę **Nagłówek**.

1. Rozwiń skróconą kartę **Adres**, a następnie wybierz pozycję **Inny adres** na pasku narzędzi Skrócona karta.

1. W oknie dialogowym **Wybór adresu** wybierz **Zlecenia serwisowe** z listy rozwijanej nad siatką.

1. Wybierz adres i wybierz **OK**, aby skopiować go do zlecenia serwisowego.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]