---
title: Resetowanie składnicy danych FAQ
description: Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące resetowania składnicy danych.
author: jinniew
ms.date: 06/09/2021
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
ms.openlocfilehash: 7cd96c7bc698986ef1ef07ca88479a3d49f22924
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266616"
---
# <a name="data-mart-resets-faq"></a>Resetowanie składnicy danych FAQ

Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące resetowania składnicy danych. Zresetowanie składnicy danych może być procesem czasochłonnym i w zależności od okoliczności może nie być rozwiązaniem, które jest wymagane. Dlatego ten temat zawiera informacje o okolicznościach, w których reset składnicy danych może pomóc, a także o okolicznościach, w których jest to mało prawdopodobne.

## <a name="what-is-a-data-mart-reset"></a>Co to jest reset zbiorczej bazy danych?

Reset składnicy danych wyłączy zadania integracji, usunie wszystkie dane składnicy danych, a następnie ponownie włączy integrację.

Aby zapewnić, że stare dane nie zostaną wstawione, reset składnicy danych może zostać uruchomiony dopiero po zakończeniu istniejących zadań. W przypadku próby zresetowania składnicy danych przed wykonaniem wszystkich zadań może zostać wyświetlony komunikat o następującej treści: „Resetowanie danych nie zostało przetworzone z powodu aktywnego zadania. Spróbuj ponownie później”.

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a>Kiedy mogę zresetować składnicę danych?

Jeśli do danej sytuacji ma zastosowanie co najmniej jedno z następujących sprawozdań, organizacja może skorzystać z resetowania danych:

- Baza danych aplikacji została przywrócona.
- Otworzyłeś zgłoszenie do działu wsparcia technicznego, a inżynier działu wsparcia technicznego polecił Ci zresetować składnicę danych w ramach rozwiązywania problemów.
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a>Kiedy nie resetować składnicy danych?

Oto kilka okoliczności, w których nie zalecamy resetowania:

- Występują problemy z wydajnością związane z synchronizacją.
- Jeśli z następujących przyczyn używasz wzorca resetowania cyklicznego:

    - **Brakujące dane** – Jeśli zauważysz, że brakuje danych, otwórz zgłoszenie do pomocy technicznej w firmie Microsoft, aby sprawdzić format raportu i ewentualne problemy z synchronizacją danych.
    - **Stan integracji zatrzymany**
    - **Nieaktualne rekordy** — nieaktualne rekordy same w sobie nie stanowią uzasadnienia resetowania składnicy danych. Jeśli zestaw danych jest duży, proces resetowania może potrwać trochę czasu, ale raczej mało prawdopodobne jest, że może spowodować poprawę.

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Czy zresetowanie danych spowoduje utratę raportów, które już zaprojektowano?

Nr Twoje raporty są przechowywane w tabelach SQL, które nie są dotknięte przez reset składnicy danych. Jeśli chcesz przegrać wszystkie zaprojektowane raporty, możesz utworzyć kopię zapasową projektów, które nie chcesz utracić. Aby utworzyć kopię zapasową projektu, otwórz Kreator raportów i przejdź do **Firma \> Firmy \> Bloki konstrukcyjne \> Eksport**.
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a>Czy wszyscy użytkownicy muszą opuścić system zanim będę mógł zresetować składnicę danych?

Nr Użytkownicy mogą kontynuować pracę w systemie podczas resetowania danych. Jednak do czasu zakończenia resetowania użytkownicy nie będą mieli dostępu do raportów, które zostały utworzone przy użyciu Financial Reporter.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
