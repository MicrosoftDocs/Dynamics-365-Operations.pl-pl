---
title: Tworzenie umów o świadczenie usług
description: W tym temacie opisano sposób korzystania z funkcji w modułach Zarządzanie serwisem oraz Zarządzanie projektami i ich księgowanie do tworzenia umów serwisowych.
author: sorenva
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a8a139d1a11cca036ace2540cba59bf2cace0db
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8677262"
---
# <a name="create-service-agreements"></a>Tworzenie umów o świadczenie usług

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób korzystania z funkcji w modułach Zarządzanie serwisem oraz Zarządzanie projektami i ich księgowanie do tworzenia umów serwisowych.

## <a name="create-a-service-agreement-from-service-management"></a>Tworzenie umowy serwisowej z Zarządzania serwisem

1. Przejdź do modułu **Zarządzanie serwisem**.
2. Wybierz opcję **Umowy serwisowe**, aby utworzyć nowy wiersz umowy serwisowej w nagłówku strony. 
3. Wybierz pozycję **Nowy**. Wprowadź opis, wybierz odwołanie do projektu w polu **Identyfikator projektu** i uzupełnij pozostałe wiersze i pola dla umowy serwisowej. Wybierz opcję **Zapisz**.
4. Na karcie **Relacje** wybierz opcję **Przedmioty serwisu** lub **Zadania serwisowe**, aby utworzyć relacje przedmiotów serwisu lub relacje zadań serwisowych dla umowy serwisowej. Przedmioty serwisu i zadania serwisowe, dla których zostały utworzone relacje, można dołączać do wierszy umowy serwisowej.
5. W dolnej połowie strony utwórz wiersze umowy serwisowej, kopiując je z szablonu serwisu lub innej umowy serwisowej albo tworząc je ręcznie.

> [!NOTE]
> W przypadku kopiowania wierszy do umowy serwisowej z innej umowy można wskazać, czy mają być również kopiowane relacje przedmiotów serwisu i relacje zadań serwisowych. W przypadku skopiowania tych relacji są one dodawane do ewentualnych relacji istniejących w umowie serwisowej. W przypadku kopiowania wierszy umowy serwisowej z szablonu serwisu relacje przedmiotów serwisu i relacje zadań serwisowych są automatycznie kopiowane jako relacje w nowych wierszach umowy serwisowej.

## <a name="create-service-agreement-lines-manually"></a>Ręczne tworzenie wierszy umowy serwisowej

1. Na stronie **Umowy serwisowe** dodaj wiersz umowy serwisowej w siatce wierszy. 
2. Wprowadź odpowiednie informacje w wierszu umowy serwisowej. 
3. Wybierz **Zapisz**, aby zapisać wiersz, a następnie zamknij stronę.

## <a name="create-a-service-agreement-from-project"></a>Tworzenie umowy serwisowej z modułu Projekt

1. Wybierz **Zarządzanie projektami i ich księgowanie**.
2. Wybierz opcję **Wszystkie projekty**.
3. Wybierz projekt z listy.
4. W **Okienku akcji** wybierz pozycję **Zarządzaj**. W grupie akcji **Nowy** wybierz opcję **Serwis**, a następnie opcję **Umowa serwisowa**.
5. Wykonaj kroki opisane w sekcji zatytułowanej **Tworzenie umowy serwisowej** wcześniej w tym temacie, aby wprowadzić odwołanie do projektu.


## <a name="related-topics"></a>Powiązane tematy

[Omówienie opracowania i ustanawiania przeglądów umów serwisowych](service-agreements.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]