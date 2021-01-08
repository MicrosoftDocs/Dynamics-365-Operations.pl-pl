---
title: Dopasowywanie umiejętności pracowników do potrzeb firmy
description: Umiejętności pracowników, kandydatów lub osób kontaktowych, umożliwiające im skuteczne wykonywanie swoich obowiązków, można śledzić. Można również określić umiejętności, które są wymagane dla danego zadania.
author: andreabichsel
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 7abaa99bdec5fcf20a63bfeb716ebb63dd3712df
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420076"
---
# <a name="align-workforce-skills-with-business-needs"></a>Dopasowywanie umiejętności pracowników do potrzeb firmy

Umiejętności pracowników, kandydatów lub osób kontaktowych, umożliwiające im skuteczne wykonywanie swoich obowiązków, można śledzić. Można również określić umiejętności, które są wymagane dla danego zadania.

Przykłady umiejętności, które można śledzić:
-   Kierownicze — zdolność do nadzorowania pracy innych.
-   Przywódcze — zdolność do kierowania pracownikami i domenami biznesowymi.
-   Planowania — zdolność do patrzenia w przyszłość, formułowania wizji i doprowadzania ich do końca.
-   HTML — umożliwia zapis kodu HTML.

Przed przypisaniem umiejętności do osoby lub zadania, utworzeniem przeszukiwania mapowania umiejętności lub profilu umiejętności, należy wprowadzić informacje o umiejętnościach na stronie **Umiejętności**. Dla każdej umiejętności można wybrać typ umiejętności i model oceniania.

## <a name="rating-models"></a>Modele oceniania
Modele oceniania pomagają w ocenie rzeczywistego poziomu umiejętności danej osoby, poziom, do osiągnięcia jakiego powinna ona dążyć lub poziom umiejętności wymagany dla zadania. Można wprowadzić maksymalnie 10 poziomów modelu klasyfikacji.  Każdy poziom w modelu oceniania ma przypisany współczynnik.  Wartość współczynnika będzie używana do normalizacji wyników umiejętności, które używają różnych modeli oceny.  Współczynnik musi być cyfrą od 0 do 9 i każdy poziom musi mieć unikatowy współczynnik.  Poziomy z wysokimi wartościami współczynników mają większą wagę w modelu oceniania.

## <a name="specify-job-skills"></a>Określanie umiejętności dla zadania
Po wprowadzeniu informacji o zadaniu można wskazać umiejętności, jakie osoba musi mieć przed rozpoczęciem pracy nad zadaniem.  Oprócz tego można określić żądany poziom każdego poziomu, a także poziom znaczenia dla każdej umiejętności. Dla różnych stanowisk może być wymagana ta sama umiejętność, ale jej poziom ważności może być różny.

## <a name="enter-skills-for-workers-applicants-or-contacts"></a>Wprowadź umiejętności dla pracowników, kandydatów lub osób kontaktowych
Można wprowadzić umiejętności docelowe lub rzeczywiste umiejętności pracowników, kandydatów lub osób kontaktowych. Umiejętność docelowa jest umiejętnością, jaką osoba planuje zdobyć. Rzeczywista umiejętność jest umiejętnością, jaką dana osoba aktualnie dysponuje.

## <a name="skill-mapping-and-skill-mapping-profiles"></a> Mapowanie umiejętności i profile mapowania umiejętności
Można utworzyć przeszukiwanie mapowania umiejętności do wyszukiwania pracownika, kandydata lub osoby kontaktowej, która posiada kwalifikacje do wykonywania określonego typu zadania. Algorytm mapowania stanowisk przeszukuje umiejętności, wykształcenie, stanowiska zaufania i doświadczenie w projektach, a następnie zwraca wyniki pasujące do wpisanego zapytania.  Na przykład może być potrzebna informacja o tym, którzy pracownicy w organizacji mają świadectwo CPA (Certified Public Accountant).

Profile mapowania umiejętności pozwalają znaleźć bieżących pracowników lub kandydatów z kwalifikacjami, które bezpośrednio odpowiadają potrzebom firmy.  Na przykład można utworzyć profil mapowania umiejętności dla otwartych stanowisk w organizacji. Tworząc profil dla konkretnego stanowiska, a następnie kopiując umiejętności, certyfikaty i wykształcenie z tego zadania w profilu, można szybko przeszukiwać pracowników, kandydatów i osoby, które odpowiadają co najmniej jednemu z kryteriów wprowadzonych w profilu, skontaktować się i wyświetlić listę elementów, których kwalifikacje najlepiej odpowiadają umiejętności wymaganym dla zadania.

> **Uwaga** Tylko pracownicy, kandydaci i osoby kontaktowe, które są zaznaczone do uwzględnienia w wyszukiwaniu mapowania umiejętności, mogą być wyświetleni na liście wyników mapowania umiejętności lub uwzględnieni w profilu umiejętności. Aby uwzględnić pracownika, kandydata lub osobę kontaktową w wyszukiwaniu mapowania, należy wybrać wartość Tak dla opcji **Uwzględnianie w mapowaniu kwalifikacji** na następujących stronach:
> 
> + Pracownik
> + Pracownik
> + Kandydat
> + Kontakty

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a>Analiza braku umiejętności i analiza profilu umiejętności
Można utworzyć analizę profilu kwalifikacji, aby wyświetlić listę kompetencji dla pracownika, kandydata lub osoby kontaktowej od określonego dnia. Można utworzyć analizę kwalifikacji do porównania umiejętności danej osoby i umiejętności, które są wymagane dla danego zadania.  


