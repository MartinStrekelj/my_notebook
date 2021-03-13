# Homework1

```matlab
function H = naloga1(besedilo,p)
% besedilo - stolpicni vektor znakov (char)
% p  - stevilo poznanih predhodnih znakov; 0, 1, 2 ali 3.
%    p = 0 pomeni, da racunamo povprecno informacijo na znak
%        abecede brez poznanih predhodnih znakov: H(X1)
%    p = 1 pomeni, da racunamo povprecno informacijo na znak 
%        abecede pri enem poznanem predhodnemu znaku: H(X2|X1)
%    p = 2: H(X3|X1,X2)
%    p = 3: H(X4|X1,X2,X3)
%
% H - skalar; povprecna informacija na znak abecede 
%     z upostevanjem stevila poznanih predhodnih znakov p

maskaBesedila = isletter(besedilo);
B = besedilo(maskaBesedila);
B = upper(B);
B = double(B);

if p == 0
    uniqueB = unique(B);
    pojavitve = histcounts(categorical(B), categorical(uniqueB));
    P = pojavitve/length(B);
    H = - P * log2(P)';
elseif p == 1
    % Calc H(P-1)
    uniqueB = unique(B);
    pojavitve = histcounts(categorical(B), categorical(uniqueB));
    P = pojavitve/length(B);
    H1 = - P * log2(P)';
    % Calc  H(P)
    P1 = [B(1:end-1), B(2:end)];
    [~, pari, mesto] = unique(P1, 'rows');
    PP = histcounts(categorical(mesto), categorical(1:length(pari))); 
    Ppp  = PP/length(mesto);
    H2 = - Ppp * log2(Ppp)';
    
    % H =  H(p) - H(p-1) 
    H = H2 - H1;
elseif p == 2
     % Calc H(P-1)
     P1 = [B(1:end-1), B(2:end)];
    [~, pari, mesto] = unique(P1, 'rows');
    PP = histcounts(categorical(mesto), categorical(1:length(pari))); 
    Ppp  = PP/length(mesto);
    H2 = - Ppp * log2(Ppp)';
    % Calc  H(P)
    P2 = [B(1:end-2), B(2:end-1), B(3:end)];
    [~, pari, mesto] = unique(P2, 'rows');
    PP = histcounts(categorical(mesto), categorical(1:length(pari))); 
    Ppp  = PP/length(mesto);
    H3 = - Ppp * log2(Ppp)';
    
    % H =  H(p) - H(p-1) 
    H = H3 - H2;
else
    % Calc H(P-1)
    P2 = [B(1:end-2), B(2:end-1), B(3:end)];
    [~, pari, mesto] = unique(P2, 'rows');
    PP = histcounts(categorical(mesto), categorical(1:length(pari))); 
    Ppp  = PP/length(mesto);
    H3 = - Ppp * log2(Ppp)';
    % Calc H(P)
    P3 = [B(1:end-3), B(2:end-2), B(3:end-1), B(4:end)];
    [~, pari, mesto] = unique(P3, 'rows');
    PP = histcounts(categorical(mesto), categorical(1:length(pari))); 
    Ppp  = PP/length(mesto);
    H4 = - Ppp * log2(Ppp)';
    
    % H =  H(p) - H(p-1) 
    H = H4 - H3;
end
```

## Tests

```matlab
>> test_naloga1('primeri', 1)
Rezultat za primer 1: 1
Cas izvajanja: 0.002512 sekund.

ans =

  logical

   1

>> test_naloga1('primeri', 2)
Rezultat za primer 2: 1
Cas izvajanja: 0.003573 sekund.

ans =

  logical

   1

>> test_naloga1('primeri', 3)
Rezultat za primer 3: 1
Cas izvajanja: 0.608173 sekund.

ans =

  logical

   1

>> test_naloga1('primeri', 4)
Rezultat za primer 4: 1
Cas izvajanja: 0.022234 sekund.

ans =

  logical

   1

>> test_naloga1('primeri', 5)
Rezultat za primer 5: 1
Cas izvajanja: 0.047948 sekund.

ans =

  logical

   1

>> test_naloga1('primeri', 6)
Rezultat za primer 6: 1
Cas izvajanja: 0.114195 sekund.

ans =

  logical

   1

>> test_naloga1('primeri', 7)
Rezultat za primer 7: 1
Cas izvajanja: 0.376291 sekund.

ans =

  logical

   1

>> test_naloga1('primeri', 8)
Rezultat za primer 8: 1
Cas izvajanja: 0.003501 sekund.

ans =

  logical

   1

>> test_naloga1('primeri', 9)
Rezultat za primer 9: 1
Cas izvajanja: 0.493800 sekund.

ans =

  logical

   1

>> test_naloga1('primeri', 10)
Rezultat za primer 10: 1
Cas izvajanja: 4.749533 sekund.

ans =

  logical

   1

>> test_naloga1('primeri', 11)
Rezultat za primer 11: 1
Cas izvajanja: 0.003151 sekund.

ans =

  logical

   1

>> test_naloga1('primeri', 12)
Rezultat za primer 12: 1
Cas izvajanja: 0.008971 sekund.

ans =

  logical

   1
```
