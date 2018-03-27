---
title: "Tworzenie umów o świadczenie usług"
description: "W tym temacie opisano sposób korzystania z funkcji w modułach Zarządzanie serwisem oraz Zarządzanie projektami i ich księgowanie do tworzenia umów serwisowych."
author: YuyuScheller
manager: AnnBe
ms.date: 02/19/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2a46173a3566a56a21add9d42c111d456b1ae7c1
ms.openlocfilehash: 517bc1b9de9b2512f42e4f32b4a19e517e349e8e
ms.contentlocale: pl-pl
ms.lasthandoff: 02/19/2018

---

# <a name="create-service-agreements"></a>Tworzenie umów o świadczenie usług

[!include[banner](../includes/banner.md)]

W tym temacie opisano sposób korzystania z funkcji w modułach Zarządzanie serwisem oraz Zarządzanie projektami i ich księgowanie do tworzenia umów serwisowych.

## <a name="create-a-service-agreement-from-service-management"></a>Tworzenie umowy serwisowej z Zarządzania serwisem

1. Przejdź do modułu **Zarządzanie serwisem**.
2. Kliknij opcję **Umowy serwisowe**, aby utworzyć nowy wiersz umowy serwisowej w nagłówku strony. 
3. Kliknij przycisk **Nowy**. Wprowadź opis, wybierz odwołanie do projektu w polu **Identyfikator projektu** i uzupełnij pozostałe wiersze i pola dla umowy serwisowej. Kliknij przycisk **Zapisz**.
4. Na karcie **Relacje** wybierz opcję **Przedmioty serwisu** lub **Zadania serwisowe**, aby utworzyć relacje przedmiotów serwisu lub relacje zadań serwisowych dla umowy serwisowej. Przedmioty serwisu i zadania serwisowe, dla których zostały utworzone relacje, można dołączać do wierszy umowy serwisowej.
5. W dolnej połowie strony utwórz wiersze umowy serwisowej, kopiując je z szablonu serwisu lub innej umowy serwisowej albo tworząc je ręcznie.

> [!NOTE]
> W przypadku kopiowania wierszy do umowy serwisowej z innej umowy można wskazać, czy mają być również kopiowane relacje przedmiotów serwisu i relacje zadań serwisowych. W przypadku skopiowania tych relacji są one dodawane do ewentualnych relacji istniejących w umowie serwisowej. W przypadku kopiowania wierszy umowy serwisowej z szablonu serwisu relacje przedmiotów serwisu i relacje zadań serwisowych są automatycznie kopiowane jako relacje w nowych wierszach umowy serwisowej.

## <a name="create-service-agreement-lines-manually"></a>Ręczne tworzenie wierszy umowy serwisowej

1. Na stronie **Umowy serwisowe** dodaj wiersz umowy serwisowej w siatce wierszy. 
2. Wprowadź odpowiednie informacje w wierszu umowy serwisowej. 
3. Naciśnij klawisze **CTRL+S**, aby zapisać wiersz, a następnie zamknij stronę.

## <a name="create-a-service-agreement-from-project"></a>Tworzenie umowy serwisowej z modułu Projekt

1. Kliknij opcję **Zarządzanie projektami i ich księgowanie**.
2. Kliknij opcję **Wszystkie projekty**.
3. Wybierz projekt z listy.
4. W **okienku akcji** kliknij pozycję **Zarządzaj**. W grupie akcji **Nowy** kliknij opcję **Serwis**, a następnie opcję **Umowa serwisowa**.
5. Wykonaj kroki opisane w sekcji zatytułowanej **Tworzenie umowy serwisowej** wcześniej w tym temacie, aby wprowadzić odwołanie do projektu.


## <a name="related-topics"></a>Powiązane tematy

[Umowy serwisowe](service-agreements.md)


