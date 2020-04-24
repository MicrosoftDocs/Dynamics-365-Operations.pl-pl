---
title: Poziomy usług składnika majątku
description: W tym temacie wyjaśniono poziomy usług składników majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35e7a55b1ba230be6bb72b20fcd805ea061b648e
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216582"
---
# <a name="asset-service-levels"></a>Poziomy usług składnika majątku

[!include [banner](../../includes/banner.md)]

 

W tym temacie wyjaśniono poziomy usług składników majątku w module Zarządzanie składnikami majątku. Poziomy usługi składników majątku są związane ze składnikami majątku i są przenoszone do żądań konserwacji i zleceń pracy. Są one używane do obliczania priorytetu zleceń pracy podczas planowania zlecenia pracy. Poziomy usług składników majątku można zmienić, jeśli wymagane są zmiany.

Aby uzyskać więcej informacji na temat konfiguracji, która jest powiązana z obliczaniem oceny wyników dla planowania zlecenia pracy, zobacz temat [Parametry modułu Zarządzania składnikami majątku](../setup-for-objects/enterprise-asset-management-parameters.md). Trzeba skonfigurować co najmniej jeden rekord domyślny dla poziomu usługi składnika majątku. Ten rekord domyślny jest używany, jeśli nie znaleziono innego dopasowania podczas planowania zlecenia pracy.

**Przykład 1:** domyślny poziom usługi, który jest używany, jeśli nie znaleziono innego dopasowania. W tym rekordzie można wybrać tylko poziom usługi.

**Przykład 2:** wysoki poziom usług używany do planowania zadań dla silnika ciężarówki Volvo. W tym rekordzie należy wybrać odpowiedni typ składnika majątku (np. **silnik ciężarówki**), producenta (**Volvo**) oraz poziom usługi.

## <a name="set-up-asset-service-levels"></a>Konfigurowanie poziomów usługi składnika majątku

1. Wybierz kolejno **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Poziomy usługi składnika majątku**.
2. Wybierz **Nowy**, aby utworzyć rekord.
3. W zależności od poziomu szczegółowości wymaganego dla poziomu usługi składnika majątku dokonaj odpowiednich wyborów w polach **Lokalizacja czynności konserwacyjnych**, **Typ składnika majątku**, **Producent**, **Model**, **Składnik majątku**, **Typ zlecenia pracy** oraz **Poziom usługi**.

    > [!NOTE]
    > Gdy poziom usługi aktywów jest używany w odniesieniu do żądań konserwacji i zleceń pracy, zarządzanie składnikami majątku przechodzi przez wszystkie rekordy poziomu usługi składnika majątku, aby sprawdzić, czy możliwe dopasowanie. W pierwszej kolejności sprawdza zawsze kombinację najbardziej szczegółową. Innymi słowy, moduł Zarządzanie składnikami majątku najpierw sprawdza dopasowanie dla pola **Typ zlecenia pracy**. Jeśli nie znaleziono dopasowania, sprawdza dopasowanie dla pola **Składnik majątku** itd. Jak widać w układzie strony **Poziomy usług składnika majątku** to zachowanie oznacza, że aby znaleźć najbardziej konkretną kombinację, moduł Zarządzanie składnikami majątku sprawdza każdy rekord od prawej do lewej pod kątem dopasowania. Jeśli nie uda się znaleźć dopasowania, jest używany rekord domyślny, który nie ma zaznaczeń w tych polach.

4. W polu **Poziom usługi** wybierz numer wskazujący poziom usługi (priorytet).


> [!NOTE]
> Jeśli zmienisz rekord poziomu usługi składnika majątku na stronie **Poziomy usługi składnika majątku** już po jego użyciu w zleceniu pracy, poziom usługi na żądaniach konserwacji i zleceniach pracy nie jest odpowiednio aktualizowany.
