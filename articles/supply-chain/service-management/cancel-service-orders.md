---
title: Anuluj zlecenia serwisowe
description: Zlecenie serwisowe lub wiersz zlecenia serwisowego można anulować z samego zlecenia serwisowego lub można anulować wiele zleceń serwisowych, uruchamiając zadanie okresowe.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 228b76d6f6f0bb048662c8e82df76f51b7cb3652
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/15/2022
ms.locfileid: "9017384"
---
# <a name="cancel-service-orders"></a>Anuluj zlecenia serwisowe   

[!include [banner](../includes/banner.md)]


Zlecenie serwisowe lub wiersz zlecenia serwisowego można anulować z samego zlecenia serwisowego lub można anulować wiele zleceń serwisowych, uruchamiając zadanie okresowe.


> [!NOTE]
> <P>Zlecenia serwisowego nie można anulować, jeśli nie pozwala na to etap, na jakim znajduje się zlecenie serwisowe, jeśli są z nim związane zapotrzebowania na towary lub jeśli zlecenie zostało już zaksięgowane.</P>


## <a name="cancel-a-service-order-in-the-service-orders-form"></a>Anulowanie zlecenia serwisowego w formularzu Zlecenia serwisowe

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**. Wybierz zlecenie serwisowe, a następnie w okienku akcji kliknij przycisk **Anuluj zamówienie**.

## <a name="cancel-a-service-order-line"></a>Anulowanie wiersza zlecenia serwisowego

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**. Kliknij dwukrotnie zlecenie serwisowe zawierające wiersz, który chcesz anulować.

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


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]