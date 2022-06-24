---
title: Typy zleceń
description: W tym artykule opisano typy zlecenia pracy w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderType
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 12745960f903ebc14208f2c8a01f076ed27a38d3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891184"
---
# <a name="work-order-types"></a>Typy zleceń

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

![Typy zleceń.](media/16-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]