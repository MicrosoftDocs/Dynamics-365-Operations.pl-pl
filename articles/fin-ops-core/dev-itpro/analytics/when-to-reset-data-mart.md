---
title: Resetowanie składnicy danych FAQ
description: Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące resetowania składnicy danych.
author: jinniew
ms.date: 03/21/2022
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
ms.openlocfilehash: ab6417a739e9a7b67b9e67d93f3bef654e55e5e4
ms.sourcegitcommit: 2c2ef3e312e7221006a9e230c9378bb4c1b4cd33
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2022
ms.locfileid: "8466419"
---
# <a name="data-mart-resets-faq"></a>Resetowanie składnicy danych FAQ

Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące resetowania składnicy danych. Zresetowanie składnicy danych może być procesem czasochłonnym i w zależności od okoliczności może nie być rozwiązaniem, które jest wymagane. Dlatego ten temat zawiera informacje o okolicznościach, w których reset składnicy danych może pomóc, a także o okolicznościach, w których jest to mało prawdopodobne.

## <a name="what-is-a-data-mart-reset"></a>Co to jest reset zbiorczej bazy danych?

Reset składnicy danych wyłączy zadania integracji, usunie wszystkie dane składnicy danych, a następnie ponownie włączy integrację.

Aby zapewnić, że stare dane nie zostaną wstawione, reset składnicy danych może zostać uruchomiony dopiero po zakończeniu istniejących zadań. W przypadku próby zresetowania składnicy danych przed wykonaniem wszystkich zadań może zostać wyświetlony komunikat o następującej treści: „Resetowanie danych nie zostało przetworzone z powodu aktywnego zadania. Spróbuj ponownie później”.

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a>Kiedy mogę zresetować składnicę danych?

Jeśli do danej sytuacji ma zastosowanie co najmniej jedno z następujących sprawozdań, organizacja może skorzystać z resetowania danych:

- **Baza danych aplikacji została przywrócona**
- **Otwarto zgłoszenie do pomocy technicznej** – inżynier pomocy technicznej polecił Ci zresetować zbiorczą bazę danych w ramach rozwiązywania problemów.
- **Duży odsetek nieaktualnych zapisów** — nieaktualne rekordy same w sobie nie stanowią uzasadnienia resetowania składnicy danych. Wysoki odsetek przestarzałych danych może obniżyć ogólną wydajność generowania raportów i integracji, a także spowodować dodatkowe użycie miejsca w bazie danych. Zalecamy wykonanie resetowania składnicy danych w celu usunięcia przestarzałych danych, gdy w składnicy danych jest więcej niż 80% nieaktualnych danych.
 
> [!NOTE]
> Na proces resetowania hurtowni danych ma wpływ liczba transakcji księgi głównej i budżetu w bazie danych. W zależności od liczby transakcji w systemie, resetowanie bazy danych można zakończyć w ciągu zaledwie 15 minut lub może zająć do czterech godzin. Jeśli jednak resetowanie trwa dłużej niż cztery godziny, zalecamy skontaktowanie się z pomocą techniczną.
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a>Kiedy nie resetować składnicy danych?

Oto kilka okoliczności, w których nie zalecamy resetowania:

- Występują problemy z integracją danych.
- Integracja programu Financial Reporter nie jest włączona. 

    - Oznacza to, że dane księgi głównej nie są już synchronizowane z tym schematem danych Financial Reporting. Financial Reporter może nie otrzymywać aktualnych numerów do raportów finansowych. Zazwyczaj dzieje się tak, jeśli od dłuższego czasu nie korzysta się z funkcji Financial Reporter.
    - Zostanie wyświetlony monit o włączenie integracji przez zresetowanie danych. Możesz kontynuować, wybierając przycisk **Tak**. Użytkownik może również wybrać opcję resetowania danych w późniejszym czasie. Po włączeniu integracji dane księgi głównej są ponownie synchronizowane w programie Financial Reporter. 
- Jeśli z następujących przyczyn używasz wzorca resetowania cyklicznego:

    - **Brakujące lub nieoczekiwane dane w raporcie** – Jeśli zauważysz, że brakuje danych, otwórz zgłoszenie do pomocy technicznej w firmie Microsoft, aby sprawdzić format raportu i ewentualne problemy z synchronizacją danych.
    - **Stan integracji zatrzymany** — jeśli zauważysz, że stan integracji jest zatrzymany, może to być spowodowane dużą liczby transakcji w systemie. Ten stan zostanie rozwiązany sam. Jeśli jednak zauważysz, że stan pomocy technicznej utknie ponad cztery godziny, otwórz bilet pomocy technicznej dla firmy Microsoft. 
   
## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Czy zresetowanie danych spowoduje utratę raportów, które już zaprojektowano?

Nr Twoje raporty są przechowywane w tabelach SQL, które nie są dotknięte przez reset składnicy danych. Jeśli chcesz przegrać wszystkie zaprojektowane raporty, możesz utworzyć kopię zapasową projektów, które nie chcesz utracić. Aby utworzyć kopię zapasową projektu, otwórz Kreator raportów i przejdź do **Firma \> Firmy \> Bloki konstrukcyjne \> Eksport**.
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a>Czy wszyscy użytkownicy muszą opuścić system zanim będę mógł zresetować składnicę danych?

Nr Użytkownicy mogą kontynuować pracę w systemie podczas resetowania danych. Jednak do czasu zakończenia resetowania użytkownicy nie będą mieli dostępu do raportów, które zostały utworzone przy użyciu Financial Reporter.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
