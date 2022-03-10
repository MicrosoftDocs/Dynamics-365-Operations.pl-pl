---
title: Tworzenie konfiguracji mapowania modeli raportowania elektronicznego (ER)
description: Ta procedura umożliwia zaprojektowanie nowego mapowania modelu raportowania elektronicznego (ER) i zastosowanie wbudowanych funkcji ER w celu efektywnego obliczania agregacji.
author: NickSelin
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2da00af487e3d85edf2401e71678d7a9fc621a672e2ba477f3195f8a06d5419b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735557"
---
# <a name="create-electronic-reporting-er-model-mapping-configurations"></a>Tworzenie konfiguracji mapowania modeli raportowania elektronicznego (ER)

[!include [banner](../../includes/banner.md)]

Ta procedura umożliwia zaprojektowanie nowego mapowania modelu raportowania elektronicznego (ER) i zastosowanie wbudowanych funkcji ER w celu efektywnego obliczania agregacji. Ta procedura dotyczy tworzenia konfiguracji dla przykładowej firmy Litware, Inc. 

Procedura ta została utworzona dla użytkowników z przypisaną rola administratora systemu lub dewelopera raportowania elektronicznego.

Kroki te można wykonać przy użyciu dowolnego zestawu danych. Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.

1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
    * Upewnij się, że dostawca konfiguracji przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako Aktywny. Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj procedurę „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.  
2. Kliknij opcję Konfiguracje raportowania.
3. Kliknij przycisk Pokaż filtry.
4. W polu „Nazwa” wprowadź wartość filtra „Intrastat” i użyj operatora filtra „zaczyna się od”.
    * Zastosowanie tego filtra pozwala znaleźć konfigurację modelu danych „Intrastat”. Model ten może już istnieć w drzewie konfiguracji. Jeśli tak, przejdź do kolejnego podzadania.   

## <a name="get-the-intrastat-model-configuration-provided-by-microsoft"></a>Pobieranie konfiguracji modelu Intrastat dostarczanej przez firmę Microsoft
1. Zamknij stronę.
2. Zamknij stronę.
3. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
4. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wybierz kafelek dostawcy Microsoft.  
5. Kliknij Repozytoria.
    * Kliknij opcję Repozytoria na kafelku dostawcy Microsoft.  
6. Kliknij przycisk Pokaż filtry.
7. W polu „Nazwa typu” wprowadź wartość filtra „zasoby” i użyj operatora filtra „zawiera”. 
8. Kliknij przycisk Otwórz.
9. W drzewie zaznacz element „Model Intrastat”.
10. Kliknij przycisk Importuj.
11. Kliknij przycisk Tak.
    * Zaimportowana została konfiguracja modelu ER zawierająca model danych, który można teraz wykorzystać do sprawdzenia działania nowych funkcji ER.  
12. Zamknij stronę.
13. Zamknij stronę.
14. Kliknij opcję Konfiguracje raportowania.

## <a name="add-a-new-model-mapping-configuration"></a>Dodawanie nowej konfiguracji mapowania modelu
1. W drzewie zaznacz element „Model Intrastat”.
2. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
3. W polu Nowy wpisz „Mapowanie modelu oparte na modelu danych Intrastat”.
4. W polu Nazwa wpisz „Przykładowe mapowanie Intrastat”.
    * Przykładowe mapowanie Intrastat  
5. Kliknij przycisk Utwórz konfigurację.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]