---
title: Przetwarzanie faktur
description: Ten temat zawiera informacje dotyczące przetwarzania faktur dla Europy Wschodniej.
author: v-kikozl
manager: AnnBe
ms.date: 07/21/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, VendParameters
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-kikozl
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 945b082528109f6f8c9292d2388749bebd4cfba4
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852491"
---
# <a name="invoice-processing"></a>Przetwarzanie faktur

[!include [banner](../includes/banner.md)]

Ten temat zawiera krótki opis scenariuszy dla określonych krajów, takich jak wewnątrzwspólnotowy podatek VAT i podatek odroczony. Wymagania prawne dla niektórych krajów europejskich wpływają na proces fakturowania. Ten temat zawiera także informacje o sposobie przetwarzania faktur odbiorców i dostawców dla tych krajów. 
<table>
<thead>
<tr>
<th>Scenariusz</th>
<th>Kraje</th>
<th>Opis zmian funkcji</th>
</tr>
</thead>
<tbody>
<tr>
<td>Daty Rozrachunków z odbiorcami i Rozrachunków z dostawcami na potrzeby podatku VAT</td>
<td>Republika Czeska, Polska</td>
<td>
<p>Przy zakupie towarów z krajów Unii Europejskiej (UE) obowiązkowe jest samodzielne obliczenie podatku VAT:</p>
<ul>
<li>Należny podatek VAT musi zostać zapłacony w okresie płatności podatku VAT, w którym wystawiono fakturę (data dokumentu).</li>
<li>Naliczonego podatku VAT nie można odliczyć przed odebraniem dokumentu (data rejestracji VAT).</li>
</ul>
<p>Aby użyć tego scenariusza, należy skonfigurować następujące ustawienia:</p>
<ul>
<li>Na stronie <strong>Parametry modułu rozrachunków z dostawcami</strong> włącz parametry <strong>Wewnątrzwspólnotowy podatek VAT</strong> i <strong>Data dokumentu na potrzeby wewnątrzwspólnotowego podatku VAT</strong>.</li>
<li>Skonfiguruj dwa kody podatków, jeden z dodatnią, a drugi z ujemną wartością procentową.</li>
<li>Skonfiguruj grupę podatku zawierającą kody podatku dodatniego i ujemnego. W przypadku kodu podatku dodatniego ustaw parametr <strong>Wewnątrzwspólnotowy podatek VAT</strong> na <strong>Tak</strong>.</li>
</ul>
<p>Po pomyślnej konfiguracji zakupy będą miały dwie zaksięgowane transakcje podatku:</p>
<ul>
<li>Transakcja dodatnia ma kierunek <strong>podatku naliczonego</strong> i datę rejestracji VAT równą dacie ze strony księgowania faktury.</li>
<li>Transakcja ujemna ma kierunek <strong>podatku należnego</strong> i datę rejestracji VAT równą dacie dokumentu.</li>
</ul>
</td>
</tr>
<tr>
<td>Zmodyfikuj datę dokumentu sprzedaży.</td>
<td>Wszystkie kraje Europy Wschodniej</td>
<td><p>Pole <strong>Data dokumentu</strong> na fakturze projektu można zmodyfikować. Ta data jest widoczna na wydrukowanej fakturze.</p>
<p>Dostępne jest także pole <strong>Data dokumentu</strong> na stronie <strong>Księgowanie faktury</strong> i <strong>Faktura niezależna</strong>. Po zaksięgowaniu faktury data dokumentu jest widoczna w nagłówku faktury.</p>
</td>
</tr>
<tr>
<td>Data dokumentu dla kursu wymiany</td>
<td>Polska, Węgry, Republika Czeska</td>
<td>
<p>Przepisy określają różne zasady wybierania prawidłowych kursów wymiany dla kursów biznesowych. W polu <strong>Data kursu wymiany</strong> na stronach <strong>Parametry modułu rozrachunków z odbiorcami</strong> i <strong>Parametry modułu rozrachunków z dostawcami</strong> można wybrać datę, która ma być używana dla kwot w obliczeniu waluty rozliczeniowej w dokumentach zakupu i sprzedaży. Podczas wprowadzania danych system pobiera kurs wymiany dla transakcji na podstawie tego parametru.</p>
<blockquote>[!NOTE]<br>Po ustawieniu pola <strong>Data kursu wymiany</strong> na <strong>Data dokumentu (tylko dla handlu z krajami UE)</strong> system używa grupy podatku. Dla grupy podatku dostępny jest parametr <strong>Handel Unijny</strong> na karcie <strong>Ogólne</strong>. Jeżeli opcja <strong>Handel Unijny</strong> jest ustawiona na <strong>Tak</strong> dla grupy podatku i jeżeli ta grupa podatku istnieje w nagłówku dokumentu, system pobiera kurs wymiany na podstawie daty dokumentu. Jeżeli opcja <strong>Handel Unijny</strong> jest ustawiona na <strong>Nie</strong> dla tej grupy podatku sprzedaży, system pobiera kurs wymiany na podstawie daty księgowania dokumentu.</blockquote>
</td>
</tr>
<tr>
<td>Daty transakcji handlowych, daty rejestracji VAT oraz kontrola daty dokumentu i VAT</td>
<td>Polska, Węgry, Republika Czeska</td>
<td>
<p>Daty sprzedaży i przyjęcia dokumentu są wymagane do raportowania podatku VAT:</p>
<ul>
<li>Data sprzedaży jest datą realizacji umowy dla transakcji w rozrachunkach z odbiorcami.</li>
<li>Data otrzymania dokumentu jest datą upoważnienia do odliczenia podatku VAT w rozrachunkach z dostawcami. Każdy odebrany dokument ma datę dla celów inspekcji.</li>
</ul>
<p>Węgierską funkcją dla daty terminów, czeską dla dat realizacji oraz polską dla daty rejestru VAT obejmują wymóg raportowania informacji podatkowych oparte na dacie różniącej się od daty księgowania.</p>
<p>Pole <strong>Data rejestru VAT</strong> obsługuje ten wymóg i jest dostępne na ponad 20 stronach. Te strony zawierają arkusze, zamówienia sprzedaży, zamówienia zakupu, faktury niezależne, arkusze faktur od dostawców i faktury projektu. Podczas aktualizacji lub księgowania dokumentów wszystkie podatki są księgowane przy użyciu odpowiedniej daty rejestru VAT i data ta jest uwzględniona na stronach, takich jak arkusze faktur dla odbiorców i dostawców.</p>
<p>W przypadku Republiki Czeskiej pole <strong>Data rejestru VAT</strong> może być puste podczas księgowania w przypadku odroczonego księgowania VAT. W przeciwnym wypadku pole jest obowiązkowe i musi zostać wypełnione.</p>
<p>Parametry weryfikacji dat można ustawić na stronie <strong>Grupy podatków</strong>:</p>
<ul>
<li>Parametry <strong>Wypełnianie daty rejestru VAT</strong> i <strong>Wypełnianie daty sprzedaży</strong> są używane jako domyślna metoda wypełniania dla odpowiednich dat. Dostępne jest także wprowadzanie ręczne i kilka metod zautomatyzowanego wprowadzania.</li>
<li>Pole <strong>Wymagana data sprzedaży</strong> określa, czy data sprzedaży musi zostać wprowadzona przed zaksięgowaniem faktury sprzedaży.</li>
</ul>
<p>Na stronie <strong>Transakcje rejestru VAT</strong> można uzupełnić puste daty rejestru VAT dla zaksięgowanych transakcji podatkowych.</p>
</td>
</tr>
<tr>
<td>Daty rejestru VAT które obejmują podatek odroczony</td>
<td>Węgry</td>
<td>
<p>Węgierskie przepisy podatkowe wymagają utworzenia faktury w momencie realizacji umowy lub nie później niż 15 po realizacji umowy.</p>
<p>Data realizacji umowy to dzień świadczenia zamówionych usług lub dostarczenia zamówionych towarów. Po aktualizacji lub zaksięgowaniu dokumentów wszystkie podatki są księgowane przy użyciu odpowiedniej daty rejestru VAT, a data jest widoczna na odpowiednich stronach. Ponadto przepisy wymagają, aby podatek VAT dotyczący ciągłego świadczenia usług, na przykład wynajmu, leasingu doradztwa czy ogrzewanie spełniał następujące kryteria:</p>
<ul>
<li>Podatek VAT musi być księgowany na dedykowanym koncie księgi głównej w dniu wystawienia faktury.</li>
<li>Podatek VAT musi zostać przeniesiony ze specjalnych kont na konto naliczonego podatku lub konto rozrachunków z dostawcami i musi zostać uwzględniony w raporcie VAT w dniu wymagalności.</li>
</ul>
<p>Aby spełnić te wymagania, można przenieść księgowania z księgi głównej na konto odroczonego podatku przychodzącego i konto odroczonego podatku wychodzącego. Jednak najpierw należy spełnić następujące warunki wstępne:</p>
<ul>
<li>Skonfiguruj konta księgi Odroczony VAT naliczony i Odroczony VAT należny w grupach księgowania.</li>
<li>Włącz parametr <strong>Odroczony VAT</strong> dla grup podatków dla towarów.</li>
</ul>
</td>
</tr>
<tr>
<td>Data obowiązkowego podatku od towarów i usług</td>
<td>Polska</td>
<td>
<p>Można wymagać, aby data rejestru VAT była zawarta w rekordach transakcji zakupu i sprzedaży. Dlatego datę rejestru VAT można przechwycić przed zaksięgowaniem transakcji. Ta funkcja ułatwia eliminację konieczności obsługi wielu transakcji na końcu okresu.</p>
<p>Pole <strong>Data rejestru VAT</strong> można ustawić jako obowiązkowe przy księgowaniu transakcji odbiorcy lub dostawcy. Aby ustawić to pole jako obowiązkowe, włącz opcję <strong>Data podatku VAT jest wymagana</strong> dla powiązanego konta odbiorcy lub dostawcy.</p>
</td>
</tr>
</tbody>
</table>
