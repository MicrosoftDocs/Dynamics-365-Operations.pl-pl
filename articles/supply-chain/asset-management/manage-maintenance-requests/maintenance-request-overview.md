---
title: Żądania konserwacji
description: Ten temat stanowi omówienie zarządzania żądaniami konserwacji w module Zarządzanie składnikami majątku
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRequestTable, EntAssetRequestWorkspace, EntAssetRequestActivePart, EntAssetRequestWorkOrderActive, EntAssetRequestType, EntAssetRequestTableCreateWO, EntAssetRequestTableLookup, EntAssetRequestTableActivePart, EntAssetMobileRequestDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 536f512abc2b7ce74ebc35dfdaf48e812a85cc2b
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6344251"
---
# <a name="maintenance-requests"></a>Żądania konserwacji

[!include [banner](../../includes/banner.md)]

Żądania konserwacji to notatki lub deklaracje utworzone w celu powiadamiania menedżera lub planisty, że składnik majątku może wymagać zadania konserwacji lub naprawy, ale bez tworzenia zlecenia pracy. Jeśli zawartość żądania konserwacji zostanie zweryfikowana i jej ważność zostanie potwierdzona, można następnie utworzyć zlecenie pracy na podstawie żądania konserwacji.

Żądania konserwacji mogą być tworzone dla dowolnego składnika majątku w module Zarządzanie składnikami majątku. Różne typy żądań konserwacji mogą być tworzone w zależności od tego, jak firma używa żądań konserwacji. Oto kilka przykładów:

- Żądania konserwacji
- Notatki
- Korekty lub ulepszenia
- Inwestycje
- Naprawa w magazynie (ten typ jest używany w przypadku odbierania składnika majątku z innej lokalizacji, dzięki czemu można wykonać zadanie konserwacji lub naprawy, a następnie zwrócić składnik majątku po ukończeniu zadania).

## <a name="view-maintenance-requests"></a>Przeglądanie żądań konserwacji

Aby wyświetlić żądania konserwacji, wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Żądania konserwacji** \> **Wszystkie żądania konserwacji**, **Aktywne żądania konserwacji** lub **Żądania konserwacji w moich lokalizacjach czynności konserwacyjnych**. Każda strona listy pokazuje wybrane informacje związane z żądaniem konserwacji.

![Przeglądanie żądań konserwacji.](media/01-manage-maintenance-requests.png)

> [!NOTE]
> Strona listy **Moje żądania konserwacji obsługi lokalizacji czynności konserwacyjnych** służy do wyświetlania listy żądań konserwacji, które zawierają lokalizacje czynności konserwacyjnych, które są powiązane z pracownikiem lub składnikami majątku zainstalowanymi w lokalizacjach czynności konserwacyjnych, które są związane z pracownikiem. (Aby uzyskać informacje na temat konfiguracji lokalizacji czynności konserwacyjnych w odniesieniu do konserwatorów, zobacz temat [Konserwatorzy i grupy pracowników](../setup-for-objects/workers-and-worker-groups.md)).
> 
> Mimo że informacje o koncie odbiorcy są dostępne w zarządzaniu usługami składników majątku (konserwacja zewnętrzna), nie jest możliwe w module Zarządzanie składnikami majątku (konserwacja wewnętrzna).

Aby otworzyć widok szczegółów rekordu, na stronie listy **Wszystkie żądania konserwacji** w widoku siatki wybierz łącze w kolumnie **Żądanie konserwacji**.

![Zobacz szczegóły dotyczące żądania konserwacji.](media/02-manage-maintenance-requests.png)

Przyciski w okienku akcji są zorganizowane na kartach. Poniższa tabela zawiera krótkie opisy przycisków związanych z zarządzaniem składnikami majątku.

| Nazwa przycisku                      | Opis |
|----------------------------------|-------------|
| Edycja                             | Edytuj wybrane żądanie konserwacji. |
| Nowy element                              | Utwórz nowe żądanie konserwacji. |
| Usuwanie                           | Usuwanie wybranego żądania konserwacji. |
| Pula zleceń pracy                  | Połącz wybrane żądanie konserwacji z pulą zleceń pracy. |
| Zlecenie pracy                       | Utwórz zlecenie pracy na podstawie wybranego żądania konserwacji. |
| Usterka składnika majątku                      | Kliknij **Usterki składników majątku**, gdzie można utworzyć rejestracje usterek na wybranym żądaniu konserwacji. |
| Zlecenia pracy                      | Pokaż listę wszystkich zleceń pracy, które są podłączone do wybranego żądania konserwacji. |
| Aktualizuj stan żądania konserwacji | Aktualizuj stan żądania konserwacji. |
| Dziennik stanu cyklu życia              | Wyświetl dziennik pokazujący stany cyklu życia wybranego żądania konserwacji. |
| Szczegóły żądania konserwacji      | Wydrukuj raport pokazujący szczegóły wybranego żądania konserwacji. |
| Wyślij użyczony składnik majątku                  | Wybierz użyczony składnik majątku, który powinien być tymczasowy zamiennikiem składnika majątku wybranego w wybranym żądaniu konserwacji. |
| Zwróć użyczony składnik majątku                | Zarejestruj użyczony składnik majątku jako zwrócony. |



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]