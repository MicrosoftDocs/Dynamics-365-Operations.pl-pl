---
title: Dodawanie adresu do zlecenia serwisowego
description: W tym temacie opisano sposób dodawania adresu odbiorcy do zlecenia serwisowego.
author: ShylaThompson
manager: tfehr
ms.date: 05/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7b9c6a410acbfebb3a83e753c422dd87dbf52566
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205864"
---
# <a name="add-an-address-to-a-service-order"></a>Dodawanie adresu do zlecenia serwisowego    

[!include [banner](../includes/banner.md)]


W tym temacie opisano sposób dodawania adresu odbiorcy do zlecenia serwisowego. Podczas tworzenia zlecenia serwisowego informacje adresowe są przenoszone z projektu, do którego jest dołączone zlecenie serwisowe. Jednak można wybrać alternatywną lokalizację z adresów, które zostały już wprowadzone w Microsoft Dynamics AX dla odbiorców, dostawców, oddziałów, magazynów, zleceń serwisowych i projektów.

Można również utworzyć nowy adres. Domyślnie nowy adres zostanie przeniesiony do projektu. Można jednak określić, że nowy adres jest odpowiedni tylko dla tego wystąpienia usługi. W takim przypadku nowy adres nie zostanie przeniesiony do projektu.

## <a name="create-a-customer-address-for-a-service-order"></a>Tworzenie adresu odbiorcy dla zlecenia serwisowego

Aby dodać adres do zlecenia serwisowego, wykonaj następujące czynności:

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.

2.  Otwórz zlecenie serwisowe, dla którego chcesz utworzyć adres.

3.  W **okienku akcji** kliknij przycisk **Edytuj**, a następnie kliknij opcję **Widok nagłówka**.

4.  Na skróconej karcie **Adres** kliknij przycisk **Dodaj adres**.

5.  W formularzu **Nowy adres** wprowadź niepowtarzalną nazwę dla adresu i wypełnij pozostałe pola. 
    

    > [!WARNING]
    > <P>Jeśli wprowadzisz taką samą nazwę jak istniejący adres, informacje wprowadzone w pozostałych polach zastąpią informacje istniejącego adresu.</P>


6.  Kliknij **OK**, aby skopiować nowy adres do zlecenia serwisowego.

## <a name="specify-an-alternative-address-on-a-service-order"></a>Określanie adresu alternatywnego dotyczącego zlecenia serwisowego

Aby dodać inny adres do zlecenia serwisowego, wykonaj następujące czynności:

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.

2.  Otwórz zlecenie serwisowe, dla którego chcesz wprowadzić inny adres.

3.  W **okienku akcji** kliknij przycisk **Edytuj**, a następnie kliknij opcję **Widok nagłówka**.

4.  Na skróconej karcie **Adres** kliknij przycisk **Inny adres**.

5.  W formularzu **Wybór adresu** w polu **Typ rekordu** zaznacz **Zlecenia serwisowe**.

6.  Wybierz adres i kliknij **OK**, aby skopiować go do zlecenia serwisowego.


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]