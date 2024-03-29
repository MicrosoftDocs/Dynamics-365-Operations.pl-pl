---
title: Tworzenie i obsługa blokowania zapasów
description: W tym artykule opisano sposób korzystania z funkcji blokowania zapasów, aby zapobiec rezerwowaniu fizycznie dostępnych zapasów przez inne dokumenty źródłowe.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ba95b689bedfc76598dfa81548a074f4fb7c833a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859351"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>Tworzenie i obsługa blokowania zapasów

[!include [banner](../../includes/banner.md)]

W tym artykule opisano sposób korzystania z funkcji blokowania zapasów, aby zapobiec rezerwowaniu fizycznie dostępnych zapasów przez inne dokumenty źródłowe. Przed rozpoczęciem procedury opisanych w tym artykule musisz mieć fizycznie dostępne zapasy towaru.

## <a name="block-inventory"></a>Blokuj zapasy

Aby utworzyć rekord blokowania zapasów w celu zablokowania zapasów, należy wykonać następujące kroki.

1. Kliknij kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Blokowanie zapasów**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nagłówku nowego rekordu blokowania ustaw w polu **Kod towaru** towar, który chcesz zablokować, i wprowadź opis.
1. Na skróconej karcie **Ogólne** w polu **Ilość** wpisz liczbę towarów do zablokowania.
1. Na skróconej karcie **Wymiary magazynowe** określ lokalizację i magazyn, w którym znajdują się zablokowane towary.
1. Na okienku akcji wybierz opcję **Zapisz**.

## <a name="update-the-conditions-of-the-inventory-blocking"></a>Aktualizowanie warunków blokowania zapasów

Aby zaktualizować rekord blokowania zapasów, wykonaj następujące czynności.

1. Kliknij kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Blokowanie zapasów**.
1. W okienku listy wybierz odpowiedni rekord blokowania.
1. Edytuj rekord stosownie do potrzeb. Możesz na przykład zmienić wartość pola **Oczekiwana data**, aby wskazać, kiedy zablokowane zapasy powinny stać się dostępne do rezerwacji. Jeśli jest wybrana opcja **Oczekiwane przyjęcia**, data będzie wyświetlana w oczekiwanej transakcji. (Opcja **Oczekiwane przyjęcia** jest domyślnie wybrana, gdy ręcznie tworzysz rekord blokowania).
1. Na okienku akcji wybierz opcję **Zapisz**.

## <a name="unblock-inventory"></a>Odblokowywanie zapasów

Aby usunąć rekord blokowania zapasów w celu odblokowania zapasów, należy wykonać następujące kroki.

1. Kliknij kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Blokowanie zapasów**.
1. W okienku listy wybierz odpowiedni rekord blokowania.
1. W okienku akcji wybierz opcję **Usuń**.
1. Zostanie wyświetlony monit o potwierdzenie operacji. Wybierz przycisk **Tak**, aby kontynuować.
1. Zamknij stronę.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
