---
title: Anuluj zlecenia serwisowe
description: Zlecenie serwisowe lub wiersz zlecenia serwisowego można anulować z samego zlecenia serwisowego lub można anulować wiele zleceń serwisowych, uruchamiając zadanie okresowe.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
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
ms.openlocfilehash: b60feec05e923c25e0f0bacb28b510906d5f73cd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974696"
---
# <a name="cancel-service-orders"></a>Anuluj zlecenia serwisowe   

[!include [banner](../includes/banner.md)]


Zlecenie serwisowe lub wiersz zlecenia serwisowego można anulować z samego zlecenia serwisowego lub można anulować wiele zleceń serwisowych, uruchamiając zadanie okresowe.


> [!NOTE]
> <P>Zlecenia serwisowego nie można anulować, jeśli nie pozwala na to etap, na jakim znajduje się zlecenie serwisowe, jeśli są z nim związane zapotrzebowania na towary lub jeśli zlecenie zostało już zaksięgowane.</P>


## <a name="cancel-a-service-order-in-the-service-orders-form"></a>Anulowanie zlecenia serwisowego w formularzu Zlecenia serwisowe

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**. Wybierz zlecenie serwisowe, a następnie w okienku akcji kliknij przycisk **Anuluj zamówienie**.

## <a name="cancel-a-service-order-line"></a>Anulowanie wiersza zlecenia serwisowego

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**. Kliknij dwukrotnie zlecenie serwisowe zawierające wiersz, który chcesz anulować.

2.  Zaznacz wiersz zlecenia serwisowego, który chcesz anulować, a następnie kliknij opcję **Anulowanie wiersza zamówienia**, aby zmienić stan wiersza na **Anulowano**.


> [!TIP]
> <P>Aby wycofać anulowanie wiersza zlecenia serwisowego i zmienić stan z powrotem na <STRONG>Utworzono</STRONG>, kliknij przycisk <STRONG>Cofnij anulowanie</STRONG>.</P>


## <a name="cancel-multiple-service-orders"></a>Anulowanie wielu zleceń serwisowych

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Okresowe** \> **Zlecenia serwisowe** \> **Anuluj zlecenia serwisowe**.

2.  Kliknij przycisk **Wybierz**.

3.  W formularzu **Informacje** w kolumnie **Kryteria** zaznacz zlecenia serwisowe, które chcesz anulować.

4.  Kliknij przycisk **OK**, aby zamknąć formularz **Informacje**.

5.  Zaznacz pole wyboru **Pokaż dziennik informacyjny**, aby wygenerować dziennik informacyjny pokazujący anulowane zlecenia serwisowe.

6.  Zaznacz pole wyboru **Cofnij anulowanie**, jeśli chcesz cofnąć stan **Anulowano** zlecenia serwisowego.

7.  Kliknij przycisk **OK**.

Zaznaczone zlecenia serwisowe zostaną anulowane lub ich stan postępu **Anulowano** zostanie cofnięty do stanu **W toku**.


> [!NOTE]
> <P>W przypadku zaznaczenia pola wyboru <STRONG>Cofnij anulowanie</STRONG> zlecenia serwisowe znajdujące się w stanie postępu <STRONG>Anulowano</STRONG> zostaną wycofane, a zlecenia serwisowe znajdujące się w stanie postępu <STRONG>W toku</STRONG> nie zostaną anulowane.</P>


  


