---
title: Kiedy resetować składnicę danych
description: W tym temacie wymieniono okoliczności, które mogą zostać poprawione przez zresetowanie składnicy danych, i okoliczności, w których zresetowanie składnicy danych nie będzie pomocne.
author: jinniew
manager: AnnBe
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1c1524c7a1a3fbe71c51b23571996d87641cdf7e
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093219"
---
# <a name="when-to-reset-a-data-mart"></a>Kiedy resetować składnicę danych

Resetowanie składnicy danych może być czasochłonne. W zależności od okoliczności ta akcja może nie być potrzebnym rozwiązaniem. W tym temacie wymieniono okoliczności, które mogą zostać poprawione przez zresetowanie składnicy danych, a także okoliczności, w których zresetowanie składnicy danych nie będzie pomocne.  

## <a name="when-do-you-need-to-do-a-data-mart-reset"></a>Kiedy musisz zresetować składnicę danych?
Przed zresetowaniem składnicy danych należy zadać sobie poniższe pytania. Odpowiedź Tak na jedno lub więcej pytań może wskazywać, że organizacja może skorzystać z zalet zresetowania składnicy danych.

- Baza danych aplikacji została przywrócona, ale baza danych składnicy danych nie.
- W okresie księgowym są niepoprawne dane, które nie są wynikiem problemu z projektem raportu.
- W okresie księgowym są widoczne niepoprawne dane i rekordy są wymienione w obszarze Próby integracji na stronie **Stan integracji** w projektancie raportów (uruchom projektanta raportów i wybierz opcję **Narzędzia > Stan integracji**).
- Otwarto zdarzenie pomocy technicznej, a inżynier pomocy technicznej zlecił zresetowanie składnicy danych w ramach kroku rozwiązywania problemów.
 
## <a name="when-its-not-appropriate-to-reset-a-data-mart"></a>Kiedy resetowanie składnicy danych nie jest właściwym rozwiązaniem?
Istnieją pewne okoliczności, w przypadku których nie zaleca się resetowania składnicy danych. Obejmują one następujące sytuacje. 

- Wszystkie okoliczności, których przyczyna nie jest wymieniona w tym temacie.
- Występują problemy z wydajnością związane z synchronizacją danych. W tym wypadku zresetowanie składnicy danych prawdopodobnie nie pomoże.
- Jeśli z następujących przyczyn używasz wzorca resetowania cyklicznego: 
  - **Brakujące dane** — najpierw wyeliminuj problemy z projektem raportu i problemy z synchronizacją danych. Można np. zwrócić uwagę, że mapa informacji nie została uruchomiona od czasu zaksięgowania brakujących danych.
  - **Stan zablokowanej integracji** — jeśli integracja jest wolna lub prawdopodobnie zablokowana, zresetowanie składnicy danych prawdopodobnie nie rozwiąże problemu.
  - **Próby zresetowania zostały zakończone niepowodzeniem** — jeśli dokonano kilku prób zakończenia tego resetowania i z powodu brakujących danych zostały one zakończone niepowodzeniem, zalecane jest otwarcie zdarzenia pomocy technicznej i praca z inżynierem pomocy technicznej w celu przeanalizowania sytuacji przed podjęciem próby ponownego zresetowania składnicy danych.
  - **Nieaktualne rekordy** — nieaktualne rekordy same w sobie nie stanowią uzasadnienia resetowania składnicy danych. Jeśli zestaw danych jest duży, proces resetowania może potrwać trochę czasu, ale może spowodować poprawę.
 
## <a name="what-a-data-mart-reset-does-not-do"></a>Czego nie powoduje zresetowanie składnicy danych  
- Resetowanie rozpocznie się tylko po ukończeniu istniejących zadań. Dzięki temu stare dane nie będą wstawiane. Na tym etapie może zostać wyświetlony następujący komunikat: „Resetowanie składnicy danych nie zostało przetworzone z powodu aktywnego zadania. Spróbuj ponownie później”.
- Zresetowanie spowoduje wyłączenie zadań integracji i usunięcie wszystkich danych składnicy. Integracja została ponownie włączona.

> [!NOTE]
> W poniższych punktach określono dwie opcje, których zresetowanie składnicy danych *nie* spowoduje. <br>
> - Resetowanie nie powoduje wyczyszczenia projektów raportów. <br>
> - Resetowanie nie powoduje wyczyszczenia danych firmy lub użytkownika, chyba że zostaną wybrane.
