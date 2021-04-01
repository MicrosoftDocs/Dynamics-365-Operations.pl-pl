---
title: Migracja do modułu Optymalizacja planowania w celu realizacji planowania głównego
description: Ten temat zawiera informacje o nowym głównym silniku planowania, optymalizacji planowania i migracji z istniejącego aparatu.
author: ChristianRytt
manager: tfehr
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: crytt
ms.search.validFrom: 2020-11-05
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5fdbe472f24e1140f0af63da8a1fc4eafe4767a2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238045"
---
# <a name="migration-to-planning-optimization-for-master-planning"></a>Migracja do modułu Optymalizacja planowania w celu realizacji planowania głównego

[!include [banner](../includes/banner.md)]

Wbudowany aparat planowania głównego jest zaplanowany jako przestarzały (przestarzały). Jest zastępowany dodatkiem optymalizacji planowania dla rozwiązania Microsoft Dynamics 365 Supply Chain Management. Ten temat zawiera informacje dotyczące wpływu na nowe i istniejące wdrożenia. Zawiera on informacje dotyczące wymaganych akcji.

Optymalizacja planowania umożliwia wykonywanie obliczeń planowania głównego poza Supply Chain Management i jego bazą danych Azure SQL. Korzyści związane z optymalizacją planowania obejmują lepszą wydajność i zminimalizowany wpływ na bazę danych SQL podczas wykonywania głównych operacji planowania. Szybkie przebiegi planowania można wykonać nawet w godzinach pracy, dzięki czemu terminarze mogą natychmiast reagować na zmiany popytu lub parametrów.

Więcej informacji na temat optymalizacji planowania, zobacz [Omówienie optymalizacji planowania](planning-optimization/planning-optimization-overview.md).

## <a name="obsolescence-of-the-existing-master-planning-engine"></a>Przydatności istniejącego aparatu planowania głównego

Firma Microsoft umożliwia przetworzenie wbudowanego aparatu planowania na korzyść optymalizacji planowania. Ta zmiana wpływa na wszystkie środowiska w chmurze. Nie ma to wpływu na instalacje lokalne. W wersji 10.0.16 i nowszych, jeśli uruchomisz wbudowane planowanie główne bez generowania planowanych zleceń produkcyjnych, pojawi się komunikat o błędzie. Jednak przebieg planowania głównego zostanie pomyślnie zakończony pomimo komunikatu o błędzie.

Aby uzyskać więcej informacji na temat przestarzałości wbudowanego silnika planowania, zobacz ogłoszenia w [Usunięte lub wycofane funkcje w Dynamics 365 Supply Chain Management](../get-started/removed-deprecated-features-scm-updates.md).

## <a name="migration-messages-and-exceptions"></a>Migracja, komunikaty i wyjątki

Właściciele istniejących środowisk, którzy korzystają z wbudowanego głównego silnika planowania bez generowania planowanych zleceń produkcyjnych, otrzymają wiadomość e-mail zawierającą szczegółowe informacje o procesie wyjątku. Zalecamy współpracę z partnerem w celu oceny i planowania migracji do optymalizacji planowania.

Jak już wspomniano, w przypadku uruchomienia wbudowanego planowania głównego bez generowania planowanych zleceń produkcyjnych pojawi się komunikat o błędzie w wersji 10.0.16 i nowszych. Ten komunikat o błędzie zawiera wskazówki dotyczące migracji i instrukcje dotyczące żądania wyjątku.

### <a name="new-deployments"></a>Nowe wdrożenia

Optymalizacja planowania powinna być traktowana jako domyślny aparat planowania głównego dla wszystkich nowych wdrożeń w chmurze. Ogólnie optymalizacja planowania powinna być używana we wszystkich nowych wdrożeniach, które nie generują planowanych zleceń produkcyjnych podczas planowania głównego. Jeśli nowe wdrożenie zależy od funkcji, których optymalizacja planowania obecnie nie obsługuje, możesz zażądać wyjątku, aby móc nadal korzystać z wbudowanego głównego silnika planowania.

### <a name="existing-deployments"></a>Istniejące wdrożenia

Właściciele istniejących wdrożeń opartych na chmurze, które są zależne od planowania głównego, powinni planować migrację do optymalizacji planowania. Jeśli implementacja zależy od funkcji, których optymalizacja planowania obecnie nie obsługuje, możesz zażądać wyjątku, aby móc nadal korzystać z wbudowanego głównego silnika planowania.

W przypadku środowisk, które obecnie używają procesów planowania głównego, które stają się przestarzałe, firma Microsoft wyśle wiadomość e-mail do administratora środowiska. Ta wiadomość e-mail zawiera informacje o działaniach, które są wymagane do migracji lub żądania wyjątku.

## <a name="the-exception-process"></a>Przetwarzanie wyjątku

Możesz zażądać wyjątku, jeśli musisz nadal korzystać z wbudowanego głównego silnika planowania, ponieważ procesy biznesowe w dużym stopniu zależą od co najmniej jednej funkcji, która nie jest obecnie zaimplementowana w optymalizacji planowania. Aby uzyskać listę dostępnych funkcji, przejrzyj [Analiza dopasowań optymalizacji planowania](planning-optimization/planning-optimization-fit-analysis.md).

Obecnie wyjątki dotyczące migracji optymalizacji planowania są istotne tylko wtedy, gdy proces planowania głównego nie obejmuje produkcji (czyli planowanych zleceń produkcyjnych, które są generowane przez planowanie główne) i wymagany jest wbudowany główny aparat planowania poza wersją 10.0.15 .

Po udostępnieniu wymaganych funkcji firma Microsoft zapewni okres karencji do wygaśnięcia wyjątku. Administrator środowiska zostanie poinformowany, gdy wymagane funkcje staną się dostępne i rozpocznie się okres karencji.

> [!NOTE]
> Możesz zażądać wyjątku tylko dla środowisk produkcyjnych, a nie dla środowisk piaskownicy. Jeśli chcesz wyłączyć błąd wyjątku optymalizacji planowania w środowisku piaskownicy typu infrastruktura jako usługa (IaaS), uruchom zapytanie SQL podane w [środowiskach piaskownicy](#faq-sandbox).

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="sandbox-environments"></a><a name="faq-sandbox"></a>Środowiska piaskownicy

Czy w środowisku piaskownicy można stosować wbudowane planowanie główne? Czy jest potrzebny wyjątek?

**Odpowiedź:** Wyjątki nie są zwykle istotne dla środowisk piaskownicy, ponieważ błąd wyjątku optymalizacji planowania nie uniemożliwia pomyślnego działania wbudowanego głównego silnika planowania. Jeśli jednak komunikat o błędzie Ci przeszkadza, możesz go wyłączyć w środowisku piaskownicy IaaS (nie Service Fabric), uruchamiając następujące zapytanie w bazie danych:

```sql
-- Insert or update an enabled flight:
DECLARE @flightName NVARCHAR(100) = 'ReqPlanningOptimizationExceptionToggle';
IF NOT EXISTS (SELECT TOP 1 1 FROM SysFlighting WHERE flightName = @flightName)
    INSERT INTO SYSFLIGHTING(FLIGHTNAME,ENABLED, FLIGHTSERVICEID,PARTITION)
    SELECT @flightName, 1, 12719367,RECID FROM DBO.[PARTITIONS];
ELSE
    UPDATE SysFlighting SET enabled = 1, flightServiceId = 12719367 WHERE flightName = @flightName;
```

### <a name="on-premises-environments"></a>Środowiska lokalne

Moje środowisko jest lokalne. Czy jest potrzebny wyjątek?

**Odpowiedź:** Nie. Wyjątek nie jest wymagany w środowiskach lokalnych. Można nadal korzystać z wbudowanego planowania głównego. Administrator środowiska będzie informowany o konieczności podjęcia jakiejkolwiek akcji.

### <a name="production-scenarios"></a>Scenariusze produkcji

Korzystamy z planowanych zleceń produkcyjnych, ale obawiam się, co się stanie, gdy przejdziemy do wersji 10.0.16. Czy należy wykonać jakiekolwiek działanie?

**Odpowiedź:** Nie należy się martwić. Można nadal korzystać z wbudowanego planowania głównego w wersji 10.0.16. Zalecamy jednak, aby ocenić, czy migrację do optymalizacji planowania można rozpocząć z bieżącą funkcjonalnością. Zalecamy również, abyś był informowany o nowych funkcjach.

### <a name="email-from-microsoft"></a>Wiadomość e-mail od Microsoft

Administrator naszego środowiska otrzymał wiadomość e-mail od firmy Microsoft. Ten e-mail stwierdza, że powinniśmy przejść do optymalizacji planowania lub poprosić o wyjątek. Czy muszę podjąć jakieś działanie?

**Odpowiedź:** Tak. Twoje środowisko będzie miało wpływ, chyba że wykonasz instrukcje zawarte w e-mailu. Możesz przejść do optymalizacji planowania przed określoną datą lub zażądać wyjątku, korzystając z łącza w wiadomości e-mail. To łącze służy do otwierania kwestionariusza. Po zakończeniu i przesłaniu tego kwestionariusza otrzymasz odpowiedź pocztą e-mail. Mimo że ten proces jest ręczny, firma Microsoft stara się odpowiedzieć w ciągu tygodnia po przesłaniu kwestionariusza.

### <a name="error-messages"></a>Komunikaty o błędach

Używam wersji 10.0.16 lub nowszej i po uruchomieniu planowania głównego pojawia się następujący komunikat o błędzie. Czy planowanie główne jest zablokowane?

> Ten komunikat o błędzie jest wyświetlany, ponieważ wbudowany główny aparat planowania był używany w scenariuszach obsługiwanych przez optymalizację planowania. Należy teraz przeprowadzić migrację do optymalizacji planowania, ponieważ bieżące wbudowane planowanie główne zostanie wycofane. Należy zauważyć, że ten przebieg planowania głównego zakończył się pomyślnie.
>
> Jeśli migracja jest silnie uzależniona od oczekujących funkcji, można zażądać wyjątku od dalszego korzystania z wbudowanego głównego silnika planowania.
>
> Wypełnij poniższy kwestionariusz, aby rozpocząć i w razie potrzeby poprosić o wyjątek od migracji do optymalizacji planowania.

**Odpowiedź:** Nie, planowanie główne nie jest zablokowane. Przebieg planowania głównego został ukończony pomyślnie i można go używać w zwykły sposób. Aby jednak uniknąć otrzymywania tego komunikatu o błędzie podczas przyszłych uruchomień planowania głównego, należy natychmiast przeprowadzić migrację do optymalizacji planowania lub zażądać wyjątku, korzystając z łącza w komunikacie o błędzie.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]