--- 
title: "Uruchamianie formatów raportowania elektronicznego (ER) w celu wykonania zliczania i sumowania"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: c6d309416a3a0c4da07a76c90246f492585deef5
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="run-electronic-reporting-er-formats-to-do-counting-and-summing"></a>Uruchamianie formatów raportowania elektronicznego (ER) w celu wykonania zliczania i sumowania

[!include [task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych. Kroki można wykonać na danych firmy DEMF.

Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 3: Używanie obliczeń do wygenerowania danych wyjściowych)”.

Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a>Testowanie tej konfiguracji pod kątem generowania raportów Intrastat
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
2. Kliknij opcję Konfiguracje raportowania.
3. W drzewie rozwiń węzeł „Model Intrastat”.
4. W drzewie rozwiń węzeł „Model Intrastat\Intrastat (Niemcy)”.
5. W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)\Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.
6. W okienku akcji kliknij pozycję Konfiguracje.
7. Kliknij opcję Parametry użytkownika.
8. W polu Ustawienia uruchamiania wybierz opcję Tak.
9. Kliknij przycisk OK.
10. Kliknij przycisk Edytuj.
11. W polu Uruchom wersję roboczą wybierz opcję Tak.
12. Kliknij przycisk Zapisz.
13. Wybierz kolejno opcje Podatek > Ustawienia > Handel zagraniczny > Parametry handlu zagranicznego.
14. Rozwiń sekcję Raportowanie elektroniczne.
15. Zaznacz konfigurację „Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.
16. Zaznacz konfigurację „Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.
17. Kliknij przycisk Zapisz.
18. Zamknij stronę.
19. Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Intrastat.
20. Kliknij opcję Dane wyjściowe.
21. Kliknij przycisk Raport.
    * Wykonaj proces generowania raportu Intrastat.  
22. W polu Od dnia ustaw wartość daty równą „2000-01-01”.
    * Zdefiniuj daty rozpoczęcia i zakończenia okresu sprawozdawczego obejmującego transakcje istniejące w formularzu.  
23. W polu Do dnia ustaw wartość daty równą „2022-12-31”.
    * Zdefiniuj daty rozpoczęcia i zakończenia okresu sprawozdawczego obejmującego transakcje istniejące w formularzu.  
24. W polu Kierunek wybierz opcję „Przyjęcia”.
25. W polu Generuj plik zaznacz opcję Tak.
26. Kliknij przycisk OK.
    * Przejrzyj utworzone dane wyjściowe z wierszami podsumowania na końcu.  
27. Kliknij przycisk Nowy.
28. Na liście oznacz wybrany wiersz.
29. W polu Kierunek wybierz opcję „Wysyłki”.
30. W polu Numer towaru wprowadź lub wybierz wartość.
31. W polu Asortyment wprowadź lub wybierz wartość.
32. W polu Waga ustaw wartość „10”.
33. W polu Kwota faktury ustaw wartość „10000”.
34. W polu Kwota statystyczna ustaw wartość „10000”.
35. Kliknij opcję Dane wyjściowe.
36. Kliknij przycisk Raport.
37. W polu Kierunek wybierz opcję „Wysyłki”.
38. Kliknij przycisk OK.
    * Przejrzyj utworzone dane wyjściowe z wierszami podsumowania na końcu. Należy zauważyć, że zmieniły się one w porównaniu z pierwszą sesją.  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a>Uruchomienie tej konfiguracji w trybie debugowania w celu przejrzenia zebranych danych inwentaryzacji i sumowania
1. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
2. W drzewie rozwiń węzeł „Model Intrastat”.
3. W drzewie rozwiń węzeł „Model Intrastat\Intrastat (Niemcy)”.
4. W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)\Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.
5. W okienku akcji kliknij pozycję Konfiguracje.
6. Kliknij opcję Parametry użytkownika.
7. W polu Uruchom w trybie debugowania wybierz opcję Tak.
8. Kliknij przycisk OK.
9. Zamknij stronę.
10. Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Intrastat.
11. Kliknij opcję Dane wyjściowe.
12. Kliknij przycisk Raport.
13. Kliknij przycisk OK.
14. Zamknij stronę.
15. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
16. W drzewie rozwiń węzeł „Model Intrastat”.
17. W drzewie rozwiń węzeł „Model Intrastat\Intrastat (Niemcy)”.
18. W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)\Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.
19. Kliknij opcję Dzienniki debugowania.
    * Należy zauważyć, że utworzono rekord dziennika debugowania dla procesu wykonywania wybranej konfiguracji.  
20. Kliknij opcję Dołącz.
21. Kliknij przycisk Otwórz.
    * Przejrzyj utworzony plik XML zawierający szczegóły inwentaryzacji i sumowania, które zostały zebrane podczas wykonywania wybranej konfiguracji.  


