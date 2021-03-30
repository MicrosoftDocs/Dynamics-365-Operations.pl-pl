---
title: Konfigurowanie magazynów dla zamówień przeniesienia
description: W tym temacie opisano, jak można skonfigurować magazyny do obsługi zamówień przeniesienia.
author: Mirzaab
manager: tfehr
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation,CustVendTransportPoint2Point
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: e01629982bb383078e90ff3dad0592371f44bd1b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206854"
---
# <a name="set-up-warehouses-for-transfer-orders"></a>Konfigurowanie magazynów dla zamówień przeniesienia 

[!include [banner](../includes/banner.md)]

W celu utworzenia hierarchii obsługującej zamówienia między magazynami można korzystać z poziomów magazynowych. Na podstawie tego ustawienia moduł planowania głównego oblicza zapotrzebowanie na towary na danym poziomie magazynowym i generuje zaplanowane zamówienia przeniesienia z przypisanego magazynu źródłowego w celu spełnienia zapotrzebowania.

1.  Kliknij kolejno **Zarządzanie zapasami > Konfiguracja > Podział magazynu > Magazyny**.

2.  Wybierz magazyn, którego zapasy mają zostać uzupełnione.

3.  Na skróconej karcie **Planowanie główne** zaznacz pole wyboru **Uzupełnianie**.

4.  W polu **Magazyn główny** wybierz magazyn, który ma zostać przypisany, jako magazyn uzupełniający. Moduł planowania głównego obliczy wymagane przeniesienie dla wybranego magazynu i wygeneruje zamówienie zaplanowanego przeniesienia z magazynu przypisanego w polu **Magazyn główny**.
   
    > [!NOTE]
    > <P>Jeśli pole <STRONG>Uzupełnianie</STRONG> pozostanie puste, wybrany magazyn będzie miał przypisany poziom magazynowy względem <STRONG>Magazynu głównego</STRONG>, lecz<STRONG>Magazyn główny</STRONG> nie będzie ustawiony jako magazyn uzupełnień.</P>

5.  Zamknij stronę, aby zastosować nowe ustawienie.


> [!TIP]
> <P>Aby przypisać magazyn uzupełnień, należy najpierw ustawić magazyn jako wymiar magazynowy na stronie <STRONG>Grupy wymiarów magazynowych</STRONG>. Na tej stronie zaznacz pole <STRONG>Aktywne</STRONG> i pole <STRONG>Plan zapotrzebowania wg wymiaru</STRONG> dla danego magazynu.</P>

## <a name="set-up-transport-lead-time"></a>Ustawianie czasu realizacji dostawy

Należy także skonfigurować czas realizacji dostawy między magazynami na stronie **Dni transportu**. 
1. Przejdź do **Zarządzanie zapasami > Ustawienia > Dystrybucja > Dni transportu**.
2. W polu **Punkt przyjęcia** wybierz **magazyn**.
3. Wybierz **Magazyn wysyłki**, **Magazyn przyjęcia** i **Dni transportu**. 
4. (Opcjonalnie) Można również ustawić czas transportu, w zależności od metody dostawy, w obszarze **Dni transportu na metodę dostawy**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]