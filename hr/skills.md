---
title: "Dopasowywanie umiejętności pracowników do potrzeb firmy"
description: "Umiejętności pracowników, kandydatów lub osób kontaktowych, umożliwiające im skuteczne wykonywanie swoich obowiązków, można śledzić. Można również określić umiejętności, które są wymagane dla danego zadania."
author: kherr75
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ae940cdbab2166d8fe3f2f396c84ed4a09c2ca7e
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017

---

# <a name="align-workforce-skills-with-business-needs"></a>Dopasowywanie umiejętności pracowników do potrzeb firmy

[!include[banner](includes/banner.md)]


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

>**Uwaga** Tylko pracownicy, kandydaci i osoby kontaktowe, które są zaznaczone do uwzględnienia w wyszukiwaniu mapowania umiejętności, mogą być wyświetleni na liście wyników mapowania umiejętności lub uwzględnieni w profilu umiejętności. Aby uwzględnić pracownika, kandydata lub osobę kontaktową w wyszukiwaniu mapowania, należy wybrać wartość Tak dla opcji **Uwzględnianie w mapowaniu kwalifikacji** na następujących stronach:

> + Pracownik
> + Pracownik
> + Kandydat
> + Kontakty

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a>Analiza braku umiejętności i analiza profilu umiejętności
Można utworzyć analizę profilu kwalifikacji, aby wyświetlić listę kompetencji dla pracownika, kandydata lub osoby kontaktowej od określonego dnia. Można utworzyć analizę kwalifikacji do porównania umiejętności danej osoby i umiejętności, które są wymagane dla danego zadania.  



<a name="see-also"></a>Informacje dodatkowe
--------

[Zasoby ludzkie](index.md)




