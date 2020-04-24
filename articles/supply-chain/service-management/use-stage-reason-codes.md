---
title: Użycie kodów przyczyn etapów
description: Kod przyczyny służy do wskazania powodu, dla którego umowa dotycząca poziomu usług została anulowana lub powodu przekroczenia terminu zamówienia usług określonego w takiej umowie.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 54dae6edb6681e1ba29709ebeeea2e5094262257
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206480"
---
# <a name="use-stage-reason-codes"></a>Użycie kodów przyczyn etapów 

[!include [banner](../includes/banner.md)]


Kod przyczyny służy do wskazania powodu, dla którego umowa dotycząca poziomu usług została anulowana lub powodu przekroczenia terminu zamówienia usług określonego w takiej umowie.

Można również określić, że kod przyczyny jest wymagany, po anulowaniu umowy SLA lub gdy przekroczy limit czasu, który jest określony w SLA dla zlecenia serwisowego.

Jeśli określono, że kod przyczyny jest wymagany, należy wprowadzić kod przyczyny w następujących sytuacjach:

  - gdy zlecenie serwisowe przechodzi w stan, w którym następuje zatrzymanie rejestrowania czasu w ramach umowy dotyczącej poziomu usług dla tego zlecenia;

  - gdy zlecenie serwisowe zostanie wycofane;

  - gdy rejestrowanie czasu zostanie zatrzymane ręcznie.

## <a name="set-up-reason-codes"></a>Ustaw kody przyczyn

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Zlecenia serwisowe** \> **Kody przyczyn etapów**.

2.  W formularzu **Kody przyczyn etapów** kliknij przycisk **Nowy**, aby utworzyć nowy kod przyczyny.

3.  W polu **Kod przyczyny etapów** wprowadź unikatowy kod przyczyny etapu.

4.  W polu **Opis** wprowadź opis kodu przyczyny etapu.

5.  Zamknij formularz, aby zapisać zmiany.

## <a name="require-reason-codes-when-a-service-level-agreement-is-canceled"></a>Wymóg podawania kodu przyczyny w wypadku anulowania umowy dotyczącej poziomu usług

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Parametry modułu Zarządzanie serwisem**.

2.  W formularzu **Parametry modułu Zarządzanie serwisem** kliknij łącze **Ogólne**, a następnie zaznacz pole wyboru **Kod przyczyny dotyczący anulowania**.

## <a name="require-reason-codes-when-the-a-service-order-exceeds-the-time-limit-that-is-set-by-the-service-level-agreement"></a>Wymóg podawania kodu przyczyny w wypadku przekroczenia terminu zamówienia usług określonego w umowie dotyczącej poziomu usług

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Parametry modułu Zarządzanie serwisem**.

2.  W formularzu **Parametry modułu Zarządzanie serwisem** kliknij łącze **Ogólne**, a następnie zaznacz pole wyboru **Kod przyczyny dotyczący przekroczenia czasu**.

## <a name="see-also"></a>Informacje dodatkowe

[Rozpoczynanie i zatrzymywanie rejestrowania czasu dla zlecenia serwisowego](start-and-stop-time-recording-on-a-service-order.md)

  


