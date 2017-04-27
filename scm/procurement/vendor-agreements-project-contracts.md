---
title: "Umowy z dostawcą z płatnością po otrzymaniu zapłaty"
description: "Ten artykuł zawiera omówienie warunków płatności po otrzymaniu zapłaty (PWP) stosowanych w umowach z dostawcami. Warunki PWP pozwalają częściowo lub całkowicie wstrzymać płatności dla dostawcy do czasu, aż zapłaci odbiorca projektu. Ten artykuł zawiera także realny przykład wykorzystania warunków PWP w projekcie."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ProjProjectsListPage
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23131
ms.assetid: 20bf1d7f-8813-4c69-9cd7-576884a7e169
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 0ca75dbd00ad260c911a323f17717d0ff83331dd
ms.lasthandoff: 03/31/2017


---

# <a name="pay-when-paid-vendor-agreements"></a>Umowy z dostawcą z płatnością po otrzymaniu zapłaty

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera omówienie warunków płatności po otrzymaniu zapłaty (PWP) stosowanych w umowach z dostawcami. Warunki PWP pozwalają częściowo lub całkowicie wstrzymać płatności dla dostawcy do czasu, aż zapłaci odbiorca projektu. Ten artykuł zawiera także realny przykład wykorzystania warunków PWP w projekcie.

Po zaakceptowaniu dostawcy jako podwykonawcy w projekcie, użytkownik może wstrzymać płatność dla dostawcy lub podwykonawcy dopóki jego odbiorca nie dokona płatności za projekt. Aby wstrzymać płatności dla dostawcy, należy zdefiniować warunki płatność po otrzymaniu zapłaty (pay-when-paid — PWP) podczas konfigurowania zamówienia zakupu z dostawcą. Podczas tworzenia zamówienia zakupu dla dostawcy i przypisywaniu identyfikatora projektu do zamówienia zakupu, warunki PWP w projekcie są skojarzone z zamówieniem zakupu i dostawcą. Na stronie **Faktury od dostawcy z opcją płać, gdy zapłacone** można wyświetlić listę niezapłaconych faktury od dostawcy dla zamówienia zakupu oraz skojarzonych faktur dla odbiorcy. Ten formularz pozwala określić, czy i ile należy zapłacić dostawcy. Na przykład jeśli odbiorca zapłaci kwotę faktury projektu, użytkownik może zwolnić do zapłaty część lub całość faktur dla powiązanego dostawcy. Można ustawić warunki PWP w taki sposób, że dostawca otrzymuje zapłatę po otrzymaniu od odbiorcy określonego procenta powiązanej płatności. Po otrzymaniu częściowej płatności od odbiorcy, użytkownik może ręcznie zwolnić do zapłaty niektóre faktury dla powiązanego dostawcy. Poniższy przykład pokazuje, jak za pomocą warunków PWP można wstrzymać płatności dla dostawcy pod podwykonawcy do czas dokonania zapłaty przez odbiorcę. Twoja organizacja zawiera umowę z odbiorcą na dostarczenie 100 komputerów, na których instalujesz oprogramowanie wymagane przez odbiorcę. Uzgodniona cena wynosi 150,00 za każdy komputer. Podpisujesz umowę na dostawę komputerów z dostawcą zewnętrznym. Odbiorca chce zatwierdzić jakość komputerów, zanim zapłaci za nie Twojej organizacji. Zasady obowiązujące w Twojej organizacji wymagają wstrzymania zapłaty dla zewnętrznego zapłaty, dopóki odbiorca nie zapłaci za projekt. Ustawiasz więc projekt z wartością PWP 100%, aby wstrzymać wszystkie płatności dla dostawcy do czasu otrzymania pełnej zapłaty za fakturę dla odbiorcy. Jeden komputer kosztuje u dostawcy 100,00. Gdy dostawca wysyła Ci komputery, wysyłka zawiera fakturę na 10 000,00 za 100 komputerów. Ponieważ masz ustawiony projekt z warunkami PWP, nie płacisz dostawcy. Po otrzymaniu komputerów od dostawcy, instalujesz na nich wymagane oprogramowanie. Wraz z komputerami wysyłasz odbiorcy fakturę na 15 000,00. Odbiorca sprawdza komputery i zatwierdza jakości produktu. Następnie płaci pełną kwotę faktury projektu. Po otrzymaniu pełnej płatności od odbiorcy, płacisz dostawcy całą kwotę faktury — 10 000,00.




