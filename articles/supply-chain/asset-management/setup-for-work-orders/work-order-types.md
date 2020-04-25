---
title: Typy zleceń pracy
description: W tym temacie opisano typy zlecenia pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 375b18a4bd37ddadecee03a01b3b2125f5cc8d0a
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215431"
---
# <a name="work-order-types"></a>Typy zleceń pracy

[!include [banner](../../includes/banner.md)]

 

Typy zleceń pracy służą do klasyfikowania zleceń. Na przykład mogą istnieć typy zleceń pracy, które są związane z konserwacją prewencyjną lub naprawczą.

Typ zlecenia pracy definiuje przynależność do modelu cyklu życia zlecenia pracy. Model cyklu życia zlecenia pracy określa Stany cyklu życia zlecenia pracy, które można ustawiać w zleceniu pracy. (Przykłady stanów cyklu życia zlecenia pracy **Utworzone**, **W trakcie przetwarzania** i **Zakończone**).

Aby uzyskać więcej informacji na temat stanów cyklu życia zlecenia pracy i etapów projektu należy zapoznać się z [Stany cyklu życia zlecenia pracy](work-order-lifecycle-states.md).

1. Wybierz **Zarządzanie składnikami majątku** \> **Konfiguracja** \> **Zlecenia pracy** \> **Typy zleceń pracy**.
2. Wybierz pozycję **Nowy**, aby utworzyć nowy typ zlecenia pracy.
3. W polu **Typ zlecenia pracy** wprowadź identyfikator typu zlecenia pracy.
4. W polu **Nazwa** wprowadź nazwę.
5. W polu **Model cyklu życia zlecenia pracy** wybierz model cyklu.
5. Ustawienie opcji **Jeden konserwator** na **Tak**, jeśli wszystkie zadania zlecenia pracy powiązane z danym typem zlecenia pracy powinny zostać zaplanowane do tego samego konserwatora.
6. W polu **Typ kosztu** wybierz odpowiednio **Korygujący**, **Zapobiegawczy** lub **Inwestycyjny**. Wszystkie zadania zlecenia pracy w zleceniu pracy muszą mieć ten sam typ kosztu.
7. W sekcji **Obowiązkowe** ustaw odpowiednie opcje na **Tak**, aby określić, które informacje związane z błędami lub przerwami konserwacyjnymi są dodawane do zlecenia tego typu.

    > [!NOTE]
    > Opcje dostępne w sekcji **Obowiązkowe** są powiązane z opcjami na karcie skróconej **Weryfikuj** na stronie **Stany cyklu życia zlecenia pracy** (**Zarządzanie składnikami majątku** \> **Konfiguracja** \> **Zlecenia pracy** \> **Stany cyklu życia**).

8. Wybierz opcję **Zapisz**.

![Typy zleceń pracy](media/16-setup-for-work-orders.png)
