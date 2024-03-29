---
title: Zaplanowane wykonanie
description: W tym artykule opisano zaplanowane wykonanie w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5e9d6af5c224f683481378da57708fda3c1b7207
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848057"
---
# <a name="scheduled-execution"></a>Zaplanowane wykonanie

[!include [banner](../../includes/banner.md)]

 

Do skonfigurowania zaplanowanego wykonania można używać poziomów usługi zlecenia pracy. (Aby uzyskać więcej informacji na temat poziomów usługi zlecenia pracy, zapoznaj się z [Poziom i opis usługi](service-level-and-description.md).) Zaplanowane wykonanie zapewnia elastyczność w planowaniu pracy dla pracowników konserwacji, ponieważ istnieje możliwość skonfigurowania bardziej szczegółowych lub mniej szczegółowych wymagań dotyczących interwału, w którym zlecenie pracy powinno zostać zrealizowane. Na przykład konserwator, który wykonuje zadanie szybciej, niż oczekiwano w obiekcie produkcyjnym, może mieć możliwość przejścia do innego zaplanowanego zadania, które było planowane w bieżącym tygodniu, ale niekoniecznie w bieżącym dniu. Takie podejście umożliwia optymalizację planowania pracowników i ukończenia zadań.

Konfiguracja planowania wykonania, która jest związana z zleceniami pracy, może być rodzajowa lub konkretna. Można skonfigurować wiersze ogólne, które nie są ograniczone do określonych typów zleceń pracy, typów składników majątku itd. Można również utworzyć zaplanowane wiersze wykonania, które mają zastosowanie do określonego typu zlecenia, typu składnika majątku, typu zadania konserwacji itd.

1. Wybierz **Zarządzanie składnikami majątku** \> **Konfiguracja** \> **Zlecenia pracy** \> **Zaplanowane wykonanie**.
2. Wybierz **Nowe**, aby utworzyć nowy wiersz zaplanowanego wykonania.
3. W polach **Lokalizacja czynności konserwacyjnych**, **Typ zlecenia pracy**, **Typ składnika majątku**, **Producent**, **Model**, **Kategoria typu zadania konserwacji**, **Typ zadania konserwacji**, **Wariant typu zadania konserwacji** i **Handel** wybierz wymagane wartości.
4. W polu **Poziom usług** wybierz poziom usługi zlecenia pracy. Jeśli to pole pozostanie puste, będzie można utworzyć najbardziej ogólny typ wiersza zaplanowanego wykonania. Aby zapoznać się z przykładowym wierszem ogólnym, należy zapoznać się z pierwszym rekordem na poniższej ilustracji. Ten wiersz umożliwia zaplanowanie wszystkich zleceń pracy bez określonego poziomu usługi zlecenia pracy dla określonej daty i godziny.
5. W polu **Zaplanowane wykonanie** wybierz interwał czasu.
6. Wybierz opcję **Zapisz**.

![Zaplanowane wykonanie.](media/20-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]