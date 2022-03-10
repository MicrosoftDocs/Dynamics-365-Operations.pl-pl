---
title: Resetowanie synchronizacji usługi Dataverse
description: W tym temacie opisano sposób rozwiązywania problemów z rekordami, które nie synchronizują się prawidłowo między Microsoft Dynamics 365 Human Resources a rozwiązaniem Human capital management (HCM) Common w Microsoft Dataverse.
author: jaredha
ms.date: 09/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-09-27
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: d6b20b6b2ae4fdbbfb27a765dfb7a1dc82fe7981
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071167"
---
# <a name="reset-dataverse-synchronization"></a>Resetowanie synchronizacji usługi Dataverse


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>Problem

Rekordy nie są synchronizowane między Microsoft Dynamics 365 Human Resources a jednostkami w rozwiązaniu Wspólnego zarządzania kapitałem ludzkim (HCM) w Microsoft Dataverse. Aby uzyskać więcej informacji o synchronizacji, przejdź do [tematu Konfiguracja integracji Dataverse](hr-admin-integration-common-data-service.md). Niepowodzenie synchronizacji może wystąpić, gdy **ponowna próba integracji Dataverse**  lub  **nieodebrane żądanie synchronizacji integracji Dataverse** zadania wsadowe utkną w stanie **Wykonywanie**.

## <a name="resolution"></a>Rozwiązanie

Niepowodzenie synchronizacji może wystąpić, gdy **ponowna próba integracji Dataverse** lub **nieodebrane żądanie synchronizacji integracji Dataverse** zadania wsadowe utkną w stanie **Wykonywanie** lub **Anulowanie**, możesz zresetować stan. W tym celu należy anulować zadanie wsadowe, korzystając ze wskazówek w [tece Resetowanie zadań wsadowych, które zablokowano](hr-admin-troubleshooting-batch-execution.md). Po anulowaniu zadania wsadowego można zresetować zadanie wsadowe, ustawiając dla niego stan **Oczekujące**. Zadanie wsadowe zostanie następnie uruchomione w następnym zaplanowanym czasie wykonywania.

1. Jeśli jeszcze tego nie zrobiłeś, włącz funkcję **Ulepszone przerywanie wsadowe** w **Zarządzaniu funkcjami**.
   1. Przejdź do strony **Zarządzanie funkcjami** (**Zarządzanie funkcjami** > **Podsumowanie** > **Administrowanie systemem**).
   2. Kliknij kartę **Wszystkie**.
   3. Wybierz **kolumnę Nazwa funkcji** i filtruj według **Ulepszone przerwanie wsadowe**.
   4. Wybierz **akcję Włącz**, jeśli nie jest jeszcze włączona.

2. Wyłączanie integracji z usługą Dataverse.
   1. Przejdź do strony **integracji Microsoft Dataverse** (**Administrowanie systemem** przejdź do **Łącza** > **Integracje** > **Konfiguracja Dataverse**).
   2. Ustaw **Włącz integracje Dataverse** na **Nie**.

3. Anuluj **zadanie wsadowe integracji Dataverse**.
   1. Otwórz **zadania wsadowe** w menu (**administrowanie systemem** przejdź do **łącza** > **zadania wsadowe** > **zadania wsadowe**).
   2. Filtruj **kolumnę Opis zadania** według **integracji**.
   3. Wybierz **zadanie wsadowe integracji Dataverse**.
   4. Na akcji na wstążce wybierz pozycję **Zadanie wsadowe**, **Wymusz anulowanie**, a następnie wybierz przycisk **Tak**, aby potwierdzić.

   > [!NOTE]
   > W zależności od tego, kiedy integracja była po raz pierwszy włączona, zadanie wsadowe może mieć **ponowioną próbę integracji Common Data Service**. Wybierz to zadanie wsadowe, jeśli jest na liście, zamiast zadania wsadowego **Ponowna próba integracji Dataverse**.

4. Usuń wszystkie zadania wsadowe integracji Dataverse.
   1. Na stronie **Zadania wsadowe** wybierz **pominięte żądanie synchronizacji synchronizacji Dataverse**, **Ponowna próba integracji Dataverse** i **Początkowa synchronizacja integracji Dataverse**.
   2. Na wstążce akcji wybierz akcję **Zmień stan**. 
   3. Wybierz **Wstrzymanie** i **OK**.
   4. Na akcji na wstążce wybierz akcję **Usuń**, a następnie wybierz przycisk **Tak**, aby potwierdzić akcję.

5. Włączanie zadań wsadowych integracji Dataverse.
   1. Przejdź do strony **integracji Microsoft Dataverse** (**Administrowanie systemem** > **Łącza** > **Integracje** > **Konfiguracja Dataverse**).
   2. Ustaw **Włącz integracje Dataverse** na **Tak**.

6. Przejdź na stronę **Zadania wsadowe** i potwierdź, że utworzono zadania wsadowe **ponawiania prób integracji Dataverse** i **błędnych żądań integracji Dataverse**.

Po odtworzeniu zadań wsadowych możesz teraz monitorować **ponowienie integracji Dataverse** zadania wsadowego, aby sprawdzić, ile czasu zajmuje wykonanie zadania. Następnie można sprawdzić, czy rekordy są poprawnie synchronizowane z rozwiązaniem HCM Common w Microsoft Dataverse.

## <a name="see-also"></a>Informacje dodatkowe

[Konfiguruj integrację z programem Dataverse](hr-admin-integration-common-data-service.md)<br>
[Resetowanie zablokowanych zadań wsadowych](hr-admin-troubleshooting-batch-execution.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
