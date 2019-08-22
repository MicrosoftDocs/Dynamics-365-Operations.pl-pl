---
title: Przychodzące i wychodzące składniki majątku
description: W tym temacie opisano sposób rejestrowania przychodzących i wychodzących składników majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 62998da7f541379296d5ac325ae29f24a42f9b7c
ms.sourcegitcommit: 871b76f8808a48d282f151144829323258ffc912
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2019
ms.locfileid: "1847558"
---
# <a name="inbound-and-outbound-assets"></a>Przychodzące i wychodzące składniki majątku

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Jeśli firma wykonuje zadania naprawy lub konserwacji na składnikach majątku, które są odbierane z innych lokalizacji lub od innych klientów, zarządzanie składnikami majątku można śledzić zarówno w odniesieniu do przychodzących składników majątku w drodze do firmy, jak i składników wychodzących, które są zwracane.

> [!NOTE]
> Jeśli chcesz używać stanów cyklu życia przychodzącego i wychodzącego do zarządzania składnikami majątku, które przychodzą i są zwracane, musisz skonfigurować stany cyklu życia żądania konserwacji oraz modele cyklu życia do obsługi tych czynności. Aby uzyskać więcej informacji, zobacz temat [Ustawienia żądań konserwacji](../setup-for-maintenance-requests/requests.md).

Konfiguracja modułu Zarządzanie składnikami majątku określa, czy można pracować z przychodzącymi i wychodzącymi składnikami majątku.

## <a name="register-assets-as-inbound"></a>Rejestrowanie składników majątku jako przychodzących

1. Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Żądania konserwacji** \> **Aktywne żądania konserwacji**.
2. Wybierz żądanie konserwacji.
3. Wybierz **Aktualizuj stan żądania konserwacji**.
4. Wybierz **Przychodzące** (lub inny stan cyklu życia utworzony dla przychodzących składników majątku), a następnie wybierz przycisk **OK**.

![Rysunek 1](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a>Rejestrowanie przychodzących składników majątku jako odebranych

1. Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Przychodzące/wychodzące** \> **Zasoby przychodzące**.
2. Wybierz składnik majątku lub żądanie konserwacji.
3. Wybierz opcję **Odbierz składniki majątku**.
4. W polu **Odebrane** wpisz datę i godzinę. Następnie wybierz opcję **OK**. Rekord zostanie usunięty ze strony listy **Przychodzące składniki majątku**.

![Rysunek 2](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a>Rejestrowanie zasobów jako wychodzących

Po ukończeniu zadania konserwacji lub naprawy można zarejestrować zasób jako zwrócony.

1. Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Żądania konserwacji** \> **Aktywne żądania konserwacji**.
2. Wybierz żądanie konserwacji.
3. Wybierz **Aktualizuj stan żądania konserwacji**.
4. Wybierz **Wychodzące** (lub inny stan cyklu życia utworzony dla zasobów wychodzących), a następnie wybierz przycisk **OK**.

## <a name="register-outbound-assets-as-delivered"></a>Rejestrowanie zasobów wychodzących jako dostarczonych

1. Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Przychodzące/wychodzące** \> **Zasoby wychodzące**.
2. Wybierz składnik majątku lub żądanie konserwacji.
3. Wybierz opcję **Dostarcz zasoby**.
4. W polu **Dostarczone** wpisz datę i godzinę. Następnie wybierz opcję **OK**. Rekord zostanie usunięty ze strony listy **Zasoby wychodzące**.
