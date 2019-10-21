---
title: Zarządzanie mapowaniem modelu ER w oddzielnych konfiguracjach ER
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może zarządzać mapowaniami modelu raportowania elektronicznego (ER) w osobnych konfiguracjach ER.
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dcf322973ea5e4afd9c828c3cbd1ebbd9972a964
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182262"
---
# <a name="manage-er-model-mapping-in-separate-er-configurations"></a>Zarządzanie mapowaniem modelu ER w oddzielnych konfiguracjach ER

[!include [task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może zarządzać mapowaniami modelu raportowania elektronicznego (ER) w osobnych konfiguracjach ER. W tym przewodniku po zadaniu utworzysz wymagane konfiguracje ER dla przykładowej firmy Litware, Inc. Aby wykonać kroki podane w tym przewodniku, należy najpierw wykonać czynności z przewodnika po zadaniu „ER Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”. 

Ponieważ konfiguracje raportowania elektronicznego są współużytkowane przez firmy, można wykonać ten przewodnik po zadaniu przy użyciu zestawu danych firmowych wybranego przez użytkownika. Funkcjonalność tego przewodnika po zadaniu jest dostępna po zainstalowaniu jednej z następujących poprawek: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 dla wersji Dynamics AX 7.0 lub https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 dla wersji Dynamics 365 for Operations.

1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
    * Sprawdź, czy dostawca konfiguracji przykładowej firmy „Litware, Inc.” jest dostępny i oznaczony jako aktywny. Jeśli ten dostawca konfiguracji nie jest widoczny, należy najpierw wykonać czynności z przewodnika po zadaniu „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.   

## <a name="add-a-new-er-model-configuration"></a>Dodawanie nowej konfiguracji modelu ER
1. Kliknij opcję Konfiguracje raportowania.
    * Dodaj nową konfigurację modelu. Nazwa musi być unikatowa w drzewie konfiguracji.  
2. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
3. W polu Nazwa wpisz „Przykładowy model danych”.
    * Przykładowy model danych  
4. Kliknij przycisk Utwórz konfigurację.
5. Kliknij przycisk Konstruktor.
6. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
7. W polu Nazwa wpisz „Element główny”.
    * Element główny  
8. Kliknij przycisk Dodaj.
9. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
10. W polu Nazwa wpisz „Firma”.
    * Firma  
11. Kliknij przycisk Dodaj.
12. W polu Opis wprowadź tekst opisujący podmiot prawny lub firmę, do której użytkownik jest zalogowany w czasie wykonywania. 
    * Opis podmiotu prawnego lub firmy, w której użytkownik był zalogowany w czasie wykonywania.  
13. Kliknij opcję Odwołanie główne.
14. Kliknij przycisk OK.
15. Kliknij przycisk Zapisz.
16. Zamknij stronę.
17. Kliknij przycisk Zmień stan.
18. Kliknij przycisk Wykonaj.
19. Kliknij przycisk OK.

## <a name="add-a-new-er-model-mapping-configuration"></a>Dodawanie nowej konfiguracji mapowania modelu ER
1. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
2. W polu Nowy wpisz „Mapowanie modelu oparte na modelu danych Przykładowy model danych”.
3. W polu Nazwa wpisz „Przykładowe mapowanie”.
    * Przykładowe mapowanie  
4. Kliknij przycisk Utwórz konfigurację.
5. Rozwiń sekcję Wymagania wstępne.
    * Należy zauważyć, że grupa wymagań wstępnych Implementacje została dodana automatycznie. Grupa zawiera wstępnie wymagany składnik, który odwołuje się do nadrzędnej konfiguracji modelu danych i jest oznaczona jako Implementacja. Oznacza to, że ta konfiguracja mapowania modelu Przykładowe mapowanie jest uważana za implementację modelu danych Przykładowy model danych. W związku z tym ten składnik zmusi moduł ER do pobrania konfiguracji mapowania modelu Przykładowe mapowanie z repozytorium ER podczas pobierania konfiguracji modelu Przykładowy model danych.   
6. Kliknij przycisk Konstruktor.
    * Należy zauważyć, że utworzona konfiguracja mapowania modelu zawiera nowe puste mapowanie o takiej samej nazwie, jak utworzona konfiguracja. Należy pamiętać, że jeśli wybrana nadrzędna konfiguracja modelu zawiera mapowania modelu, zostaną one skopiowane do nowej konfiguracji mapowania modelu.   
7. Kliknij przycisk Konstruktor.
8. W drzewie zaznacz element „Dynamics 365 for Operations\Tabela”.
9. Kliknij opcję Dodaj element główny.
10. W polu Nazwa wpisz „Firma”.
    * Firma  
11. W polu Tabela wpisz „CompanyInfo”.
    * CompanyInfo  
12. Kliknij przycisk OK.
13. W drzewie rozwiń węzeł „Firma”.
14. W drzewie rozwiń węzeł „Firma\find()”.
15. W drzewie zaznacz element „Firma\find()\Nazwa”.
16. Kliknij opcję Powiąż.
17. Kliknij przycisk Zapisz.
18. Zamknij stronę.
19. Zamknij stronę.
20. W okienku akcji kliknij pozycję Konfiguracje.
21. Kliknij opcję Parametry użytkownika.
22. W polu Ustawienia uruchamiania wybierz opcję Tak.
23. Kliknij przycisk OK.
24. Kliknij przycisk Edytuj.
25. W polu Uruchom wersję roboczą wybierz opcję Tak.

## <a name="add-a-new-er-format-configuration"></a>Dodawanie nowej konfiguracji formatu ER
1. W drzewie zaznacz element „Przykładowy model danych”.
2. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
3. W polu Nowy wpisz „Format oparty na modelu danych Przykładowy model danych”.
4. W polu Nazwa wpisz „Przykładowy format”.
    * Przykładowy format  
5. Kliknij przycisk Utwórz konfigurację.
6. Kliknij przycisk Konstruktor.
7. Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.
8. W drzewie zaznacz element „Tekst\Ciąg”.
9. Kliknij przycisk OK.
10. Kliknij kartę Mapowanie.
11. W drzewie rozwiń model„”
12. W drzewie zaznacz element „model\Firma”.
13. Kliknij opcję Powiąż.
14. Kliknij przycisk Zapisz.
15. Zamknij stronę.
    * Uruchom wersję roboczą utworzonego formatu do celów testowych.  
16. Kliknij przycisk Uruchom.
    * Na skróconej karcie Wersja kliknij przycisk Uruchom.  
17. Kliknij przycisk OK.
    * Obejrzyj wyniki dla firmy, w której jest zalogowany użytkownik uruchamiający tę konfigurację formatu. Należy zwrócić uwagę, że ta konfiguracja formatu korzysta z utworzonej konfiguracji mapowania modelu, ponieważ jest dostępna tylko jedna konfiguracja zawierająca wymagane mapowania modelu.   

## <a name="add-alternative-er-model-mapping-configuration"></a>Dodawanie alternatywnej konfiguracji mapowania modelu ER
1. W drzewie zaznacz element „Przykładowy model danych”.
2. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
3. W polu Nowy wpisz „Mapowanie modelu oparte na modelu danych Przykładowy model danych”.
4. W polu Nazwa wpisz „Przykładowe mapowanie (alternatywne)”.
    * Przykładowe mapowanie (alternatywne)  
5. Kliknij przycisk Utwórz konfigurację.
6. Kliknij przycisk Konstruktor.
7. Kliknij przycisk Konstruktor.
8. W drzewie zaznacz element „Dynamics 365 for Operations\Tabela”.
9. Kliknij opcję Dodaj element główny.
10. W polu Nazwa wpisz „Firma”.
    * Firma  
11. W polu Tabela wpisz „CompanyInfo”.
    * CompanyInfo  
12. Kliknij przycisk OK.
13. Kliknij przycisk Edytuj.
14. W drzewie zaznacz element „Ciąg\ZŁĄCZ”.
15. Kliknij opcję Dodaj funkcję.
16. W drzewie rozwiń węzeł „Firma”.
17. W drzewie rozwiń węzeł „Firma\find()”.
18. W drzewie zaznacz element „Firma\find()\Nazwa”.
19. Kliknij opcję Dodaj źródło danych.
20. W polu Formuła wpisz wartość.
    * CONCATENATE(Firma.'find()'.Nazwa, ";",  
21. W drzewie zaznacz element „Firma\find()\Firma(DataArea)”.
22. Kliknij opcję Dodaj źródło danych.
23. W polu Formuła wpisz wartość.
    * CONCATENATE(Firma.'find()'.Nazwa, ";", Firma.'find()'.DataArea)  
24. Kliknij przycisk Zapisz.
25. Zamknij stronę.
26. Kliknij przycisk Zapisz.
27. Zamknij stronę.
28. Zamknij stronę.
29. W polu Uruchom wersję roboczą wybierz opcję Tak.

## <a name="use-an-existing-er-model-mapping-configuration"></a>Używanie istniejącej konfiguracji mapowania modelu ER
1. W drzewie zaznacz element „Przykładowy model danych\Przykładowy format”.
2. Kliknij przycisk Uruchom.
    * Należy pamiętać, że wybrana wersja robocza konfiguracji formatu ER nie może zostać wykonana, ponieważ więcej niż jedna konfiguracja mapowania modelu jest dostępna dla zdefiniowanego modelu danych wybranego jako źródło danych przy uruchamianiu formatu raportowania elektronicznego.   
    * Następnie zdefiniujesz alternatywną konfigurację mapowania modelu jako tę, z której mapowania modelu będą wykorzystywane jako źródła danych dla uruchamiania formatu ER.   
3. W drzewie zaznacz element „Przykładowy model danych\Przykładowe mapowanie (alternatywne)”.
4. Wybierz opcję Tak w polu Domyślne dla mapowania modelu.
5. W drzewie zaznacz element „Przykładowy model danych\Przykładowy format”.
6. Kliknij przycisk Uruchom.
7. Kliknij przycisk OK.
    * Należy zwrócić uwagę, że domyślna konfiguracja mapowania modelu jest używana przez tę konfigurację formatu do generowania dokumentu elektronicznego (utworzony produkt wyjściowy zawiera kod firmy).  

