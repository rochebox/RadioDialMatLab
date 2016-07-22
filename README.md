# RadioDialMatLab

Hi this is the code for the new "ourPlaySound" function in matlab

function [obj] = ourPlaySound (filename)
fprintf('hello from our playsound \n')
[data, fs] = audioread(filename);
obj = audioplayer(data, fs);
play(obj);


This is the code for the "radioDial"  its currently in the form of a sketch:

%radiodial

betterNumber = 0;
lastOne = 0;
audio = audioplayer(0, 80);  
 t = 0: 0.0001: 1;                  
 
 count = 1;
 songTitle = ''
 displayWave = sin(2*pi* count * t);
 plot(t, displayWave, 'LineWidth', 3);
 title([ num2str(lastOne),  ':--> ',  songTitle  ]);
 drawnow;
 
 colors = ['y' 'm' 'c' 'r' 'g' 'b' 'k' ];
 


while(1==1)
    
   val =  board.readPin('A0');
   betterNumber = round(val*10)
   
   %FIRST Song
   if (betterNumber >= 0 &&  betterNumber <=9) && lastOne ~= 1
           if isplaying(audio)
               clear sound;
               count = 0;
           end
           audio = ourPlaySound('panorama.mp3');
           lastOne = 1  ;
           songTitle = 'The Cars -- Panorama';
           
   end
     
   %SECOND Song
    if (betterNumber >=10 &&  betterNumber <=19) && lastOne ~= 2
           if isplaying(audio)
               clear sound;
               count = 0;
           end
           audio = ourPlaySound('slimShady.mp3');
           lastOne = 2 ;
           songTitle = 'Eminem -- Slim Shady';
    end
   
    if (betterNumber >=20 &&  betterNumber <=29) && lastOne ~= 3
           if isplaying(audio)
               clear sound;
               count = 0;
           end
           audio = ourPlaySound('whatILikeAboutYou.mp3');
           lastOne = 3;
           songTitle = 'Romantics -- What I Like About You!';
    end
   
      if (betterNumber >=30 &&  betterNumber <=39) && lastOne ~= 4
           if isplaying(audio)
               clear sound;
               count = 0;
           end
           audio = ourPlaySound('ahaSong.mp3');
           lastOne = 4;
           songTitle = 'Ah-Ha -- Take On Me';
      end
    
      if (betterNumber >=40 &&  betterNumber <=50) && lastOne ~= 5
           if isplaying(audio)
               clear sound;
               count = 0;
           end
           audio = ourPlaySound('rickAshley.mp3');
           lastOne = 5;
           count = 0;
           songTitle = 'Rick Ashley -- Never Going to Give You Up';
      end
      
  
        count = count + 1;
        displayWave = sin(2*pi* count * t);
        p = plot(t, displayWave);
        p.Color = colors(round(rand(1)*6)+1);
        title([ num2str(lastOne),  ':--> ',  songTitle  ]);
        drawnow;

    
        
        if count > 400  
            count = 0;
        end
 
end
