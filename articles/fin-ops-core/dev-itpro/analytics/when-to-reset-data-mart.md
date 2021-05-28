---
title: Kiedy resetować składnicę danych
description: W tym temacie wymieniono okoliczności, które mogą zostać poprawione przez zresetowanie składnicy danych, i okoliczności, w których zresetowanie składnicy danych nie będzie pomocne.
author: jinniew
ms.date: 05/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: bc2c4ee490f3bebd6e7c91609a06f8dfedfcb628
ms.sourcegitcommit: 5916ea2a94ab9af7aac21f0fc44e194d5ce82917
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2021
ms.locfileid: "5988999"
---
# <a name="when-to-reset-a-data-mart"></a>Kiedy resetować składnicę danych

Resetowanie składnicy danych może być czasochłonne. W zależności od okoliczności ta akcja może nie być potrzebnym rozwiązaniem. W tym temacie wymieniono okoliczności, które mogą zostać poprawione przez zresetowanie składnicy danych, a także okoliczności, w których zresetowanie składnicy danych nie będzie pomocne.  

## <a name="when-do-i-need-to-do-a-data-mart-reset"></a>Kiedy muszę zresetować składnicę danych?
Przed zresetowaniem składnicy danych należy zadać sobie poniższe pytania. Odpowiedź Tak na jedno lub więcej pytań może wskazywać, że organizacja może skorzystać z zalet zresetowania składnicy danych.

- Czy baza danych aplikacji została przywrócona?
- Jeśli otworzyłeś incydent pomocy technicznej, a inżynier pomocy technicznej poinstruował Cię, aby zresetować zbiorczą bazę danych w ramach kroku rozwiązywania problemów?
 
## <a name="when-is-it-not-appropriate-to-reset-a-data-mart"></a>Kiedy resetowanie składnicy danych nie jest właściwym rozwiązaniem?
Istnieją pewne okoliczności, w przypadku których nie zaleca się resetowania składnicy danych. Obejmują one następujące sytuacje. 

- Występują problemy z wydajnością związane z synchronizacją danych. 
- Jeśli z następujących przyczyn używasz wzorca resetowania cyklicznego: 
  - **Brak danych** 
  - **Stan integracji zatrzymany** 
  - **Nieaktualne rekordy** — nieaktualne rekordy same w sobie nie stanowią uzasadnienia resetowania składnicy danych. Jeśli zestaw danych jest duży, proces resetowania może potrwać trochę czasu, ale może spowodować poprawę.
 
## <a name="what-is-a-data-mart-reset"></a>Co to jest reset zbiorczej bazy danych?
- Resetowanie rozpocznie się tylko po ukończeniu istniejących zadań. Dzięki temu stare dane nie będą wstawiane. Na tym etapie może zostać wyświetlony następujący komunikat: „Resetowanie składnicy danych nie zostało przetworzone z powodu aktywnego zadania. Spróbuj ponownie później”.
- Zresetowanie spowoduje wyłączenie zadań integracji i usunięcie wszystkich danych składnicy. Integracja została ponownie włączona.

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Czy zresetowanie danych spowoduje utratę raportów, które już zaprojektowano? 
Nie, raporty są przechowywane w tabelach SQL, na które nie ma wpływu resetowanie danych. Jeśli chcesz przegrać wszystkie zaprojektowane raporty, możesz utworzyć kopię zapasową projektów, które nie chcesz utracić. Aby je schować, otwórz Konstruktora raportów i wybierz opcje **Firma > Firmy > Bloki konstruktora > Eksportuj**.
 
## <a name="is-it-necessary-for-all-users-to-exit-the-system-to-reset-the-data-mart"></a>Czy w celu zresetowania danych konieczne jest zamknięcie systemu przez wszystkich użytkowników?
Nie, użytkownicy mogą kontynuować pracę w systemie podczas resetowania danych. Do czasu zresetowania nie będą jednak mogli uzyskać dostępu do żadnych raportów utworzonych za pomocą programu Financial Reporter. 

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
