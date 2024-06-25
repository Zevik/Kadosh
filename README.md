import React, { useState, useEffect } from 'react';

const KadoshButton = () => {
  const [showText, setShowText] = useState(false);

  useEffect(() => {
    let timer;
    if (showText) {
      timer = setTimeout(() => {
        setShowText(false);
      }, 1000); // Changed to 1000ms (1 second)
    }
    return () => clearTimeout(timer);
  }, [showText]);

  const handleClick = () => {
    setShowText(true);
  };

  return (
    <div className="flex flex-col items-center justify-center h-screen bg-amber-100">
      <button
        onClick={handleClick}
        className="px-6 py-3 text-lg text-white bg-blue-500 rounded hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-opacity-50"
      >
        ללחוץ בבקשה
      </button>
      {showText && (
        <div className="mt-8 text-8xl font-bold text-blue-600 animate-fade-in">
          קדוש קדוש קדוש
        </div>
      )}
    </div>
  );
};

export default KadoshButton;
