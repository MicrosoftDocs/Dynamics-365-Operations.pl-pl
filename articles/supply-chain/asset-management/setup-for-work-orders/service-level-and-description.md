---
title: Poziom i opis usługi
description: W tym temacie wyjaśniono poziomy usług i opisy w module Zarządzanie składnikami majątku.
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
ms.openlocfilehash: 0aa23e7fe10e684e110126bd58bd761348e44700
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215500"
---
# <a name="service-level-and-description"></a>Poziom i opis usługi

[!include [banner](../../includes/banner.md)]

 

Podczas tworzenia zlecenia pracy można określić dla niego poziomy usług i dodać do niego ogólny opis. Poziomy usługi zlecenia pracy można utworzyć na stronie **Poziomy usługi zlecenia pracy** i opisy na stronie **Opis zlecenia pracy**.

## <a name="create-a-service-level"></a>Tworzenie poziomu serwisu

1. Wybierz **Zarządzanie składnikami majątku** \> **Konfiguracja** \> **Zlecenia pracy** \> **Poziom usług**.
2. Wybierz pozycję **Nowy**.
3. W polu **Poziom usług** wprowadź poziom usług (na przykład numer).
4. W polu **Nazwa** wprowadź nazwę.

    W skróconej karcie **zlecenia pracy** można zdefiniować oczekiwane daty rozpoczęcia i zakończenia oraz godziny. Pola na skróconej karcie definiują okres, w którym zlecenia pracy powinny zostać rozpoczęte i zakończone. Są one używane dla ręcznie tworzonych zleceń pracy i zleceń roboczych tworzonych na podstawie zgłoszeń obsługi. 

5. W polu **Dzień rozpoczęcia** wprowadź liczbę dni określającą okres, w którym ma się rozpocząć zlecenie pracy. Liczba dni jest obliczana na podstawie daty utworzenia zlecenia pracy. Jeśli na przykład zlecenie pracy powinno zostać rozpoczęte po jego utworzeniu, należy wprowadzić **wartość**0. Jeśli na przykład zlecenie pracy powinno zostać rozpoczęte w ciągu tygodnia po jego utworzeniu, należy wprowadzić **7**.
6. Aby określić godzinę rozpoczęcia zlecenia pracy oprócz daty początkowej, należy w polu **Ustaw godzinę rozpoczęcia** wybrać opcję **tak**. Następnie wprowadź godzinę rozpoczęcia w polu **Godzina rozpoczęcia**. Ustawienie opcji na wartość **nie** spowoduje, że zostanie użyta bieżąca godzina dnia.
7. W polu **Dzień zakończenia** wprowadź liczbę dni określającą okres, w którym ma się zakończyć zlecenie pracy. Liczba dni jest obliczana na podstawie daty rozpoczęcia zlecenia pracy. Jeśli na przykład zlecenie pracy powinno zakończyć się w ciągu jednego tygodnia od daty rozpoczęcia, należy wprowadzić **7**.
8. Aby określić godzinę zakończenia zlecenia pracy oprócz daty zakończenia, należy w polu **Ustaw godzinę zakończenia** wybrać opcję **tak**. Następnie wprowadź godzinę zakończenia w polu **Godzina zakończenia**. Ustawienie opcji na wartość **nie** spowoduje, że zostanie użyta bieżąca godzina dnia.
9. Wybierz opcję **Zapisz**.

![Strona Poziom usługi zleceń pracy](media/19-setup-for-work-orders.png)

## <a name="create-a-description"></a>Stwórz opis

1. Wybierz **Zarządzanie składnikami majątku** \> **Konfiguracja** \> **Zlecenia pracy** \> **Opisy**.
2. Wybierz pozycję **Nowy**.
3. W polu **Opis** wprowadź opis.
4. Wybierz opcję **Zapisz**.
